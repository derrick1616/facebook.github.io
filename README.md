from storag import *
import asyncio
from pyppeteer import launch

async def main():
    browser = await launch(headless=False, executablePath=r'C:\Program Files\Chromium\Application\chrome.exe')
    page = await browser.newPage()
    
    async def generate_emails():
        number = 179
        while number < 500:
            full_name = "ebukapeter"
            gmail_art = "@gmail.com"
            emailaddress = full_name + str(number) + gmail_art
            yield emailaddress
            number += 1
    
    async def check_facebook_accounts():
        async for email in generate_emails():
            await page.goto('https://www.facebook.com/')  # Go to the main page
            
            # Clicking on "Forgotten password?" link
            await page.click('a[href*="recover/initiate"]')
            
            try:
                # Wait for the email input field to appear
                await page.waitForSelector('#identify_email')
                
                # Clearing input field
                await page.evaluate('''() => {
                    document.querySelector('#identify_email').value = '';
                }''')
                
                # Entering email address
                await page.type('#identify_email', email)
                
                # Clicking on "Search" button
                await page.click('#did_submit')
                
                # Checking if email has an account linked to it
                recover_account = await page.querySelector('#recover-account')
                if recover_account:
                    print(email)
                    continue
            except Exception as e:
                print(f"Error occurred: {e}")
                continue
            
            # Wait for some time before trying the next email (optional)
            await asyncio.sleep(5)
    
    await check_facebook_accounts()
    await browser.close()

asyncio.get_event_loop().run_until_complete(main())

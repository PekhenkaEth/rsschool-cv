# Denis Grass
<img src="https://media.tenor.com/WcX6D6YNjkIAAAAd/andrew-tate.gif" height="300px"> 

*discord: eth.1*

*email: craninft@gmail.com*

*[github](https://github.com/PekhenkaEth)*

----

## ABOUT ME
I have been working online for over 4 years. Indirectly connected with the IT sphere. 
Below I have given examples of what I have worked with. But to be clear: I have the most minimal general knowledge that helped to understand what I was doing. To implement everything that I have given, I used Google, YouTube, neural networks.

**Briefly about what I had experience with:**

* using and code simple parse3s with adding webhooks to discord

* creating requests/selenium bots that spam API sites for making orders, where speed was important 

* reverse engineering with nike website, to bypass cloudflare

* web3 contract deployments

___
## SKILLS

* Python
  * requests
  * selenium 
 
* English level B1
___

## Code snippet

```python
import os
import asyncio
import aiohttp

# Get the path to the directory where the script is located
script_dir = os.path.dirname(os.path.abspath(__file__))

# Construct the path to the cookies file
cookies_file_path = os.path.join(script_dir, 'Cookies.txt')

# Read the cookies from the file
with open(cookies_file_path, 'r') as file:
    cookies_list = file.read().splitlines()

# Ask user for Mint link
mint_link = input("Mint link: ")

# Construct the URL and Referer using the mint_link value
url = f'https://inscribenow.io/collections/{mint_link}/mint?c=5'
referer = f'https://inscribenow.io/collections/{mint_link}'

headers = {
    'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7',
    'Accept-Encoding': 'gzip, deflate, br',
    'Accept-Language': 'ru-RU,ru;q=0.9,en-US;q=0.8,en;q=0.7',
    'Dnt': '1',
    'Referer': referer,
    'Sec-Ch-Ua': '"Google Chrome";v="113", "Chromium";v="113", "Not-A.Brand";v="24"',
    'Sec-Ch-Ua-Mobile': '?0',
    'Sec-Ch-Ua-Platform': '"Windows"',
    'Sec-Fetch-Dest': 'document',
    'Sec-Fetch-Mode': 'navigate',
    'Sec-Fetch-Site': 'same-origin',
    'Sec-Fetch-User': '?1',
    'Upgrade-Insecure-Requests': '1',
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36'
}

# Ask user for desired quantity
desired_quantity = input("How many requests you want to send? ")

# Convert input to an integer
desired_quantity = int(desired_quantity)

# Function to send request with a cookie
async def send_request(cookie):
    try:
        payload = {'c': str(desired_quantity)}
        headers['Cookie'] = cookie

        async with aiohttp.ClientSession() as session:
            async with session.get(url, params=payload, headers=headers) as response:
                status = response.status
                print('Request sent for cookie:', cookie, 'Status:', status)

    except aiohttp.ClientError as e:
        print('An error occurred for cookie', cookie + ':', str(e))

# Main function to send requests
async def main():
    # Create tasks for sending requests with each cookie
    tasks = [send_request(cookie) for cookie in cookies_list]

    # Wait for all tasks to complete
    await asyncio.gather(*tasks)

# Create an event loop
loop = asyncio.get_event_loop()

# Function wrapper to run the event loop
def run_main():
    loop.run_until_complete(main())

# Run the program
if __name__ == '__main__':
    run_main()
```
___

## EDUCATION


__Bachelor's Degree in Software Engineering (2014-2018)__

__Master Degree in Finance and Credit (2019-2021)__

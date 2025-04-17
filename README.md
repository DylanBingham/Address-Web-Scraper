# Address-Web-Scraper

Note : This project is intended to be a supplement to my coding portfolio for potential employers to review.

## TLDR:
In this project I created a web scraper that can iterate through a list of URL's (specifically their contact page) and extract a full street address from the html.




## Details:
The methodology I used to match street addresses has proven very effective and works in almost all of the specific use cases I had. There is almost no full-proof way to build a regex statement that matches the complexity and variety of a street address (you will find no consistent examples online and I have created my own custom statement), however the key was to constrain the string that my regex was searching within. 

Here are the paraphrased goals of this specific project and what it accomplishes.

1. Function that takes url as arguement
2. Use urllib to get response from url, ignoring ssl
3. Use beautiful soup to read content via html parser
4. Next loop through elements of html using regex to find string that matches for City, StateAbrrev ZipCode
5. Then retrieve the parent of that tag and match for full street address using regex
6. Once found then append to list with url preceding


## Bugs to fix:
1. There are massive line breaks between street name and city in addresses[80:84] 
2. There are \r text chars in some addresses, need to replace
3. If 404/403 returned modify url to 'contact-us'
4. URLError: <urlopen error EOF occurred in violation of protocol (_ssl.c:1129)>

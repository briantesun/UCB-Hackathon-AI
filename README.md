## Yonder
Conversational Product Recommendations Designed For E-commerce

## Techstack
- Frontend: React, Typescript, Tailwind CSS, Material UI
- Backend: Node.js, LangChain, OpenAI, PineCone, Mongodb

## Inspiration
Think of your most positive shopping experiences. You may think of the time you got help from an associate at Apple's Genius Bar for your next big work purchase or that time the Ritz-Carlton receptionist helped you pick a room with a stunning view. No matter the specifics, great customer service elevates the best brands in the world. Since the inception of e-commerce, companies couldn't recreate that same experience without hiring armies of overseas or domestic employees. With our product, every company will have a nice, knowledgeable, and diligent assistant to help every customer that visits their website find the best product for them!

## What it does
Yonder Search provides a cost-effective, scalable solution for product recommendations on e-commerce websites. Any potential customer will have instant access to an assistant that'll have knowledge of the entire company's website and provide product recommendations based on what the user requests.

User: "I want a golf shoe that's good on the course on the weekends, and good in the office on weekdays." Assistant: "Thank you for considering Nike for your shoe needs. You are correct that the Air Max 1 G and Air Jordan 1 G are both versatile shoes that can be worn on and off the golf course. ..."

## How we built it
- Step 1: Scraped close to 100 shoe product pages off Nike.com (product title, link, reviews, price, and descriptions) and stored it in a CSV.

- Step 2: Used Langchain & OpenAI to convert scraped text into embeddings, and then stored those embeddings in Pinecone. Also stored the csv data in MongoDB so that we could present it in our mock ecommerce store.

- Step 3: Built a frontend with React, creating a landing page and a mock version of Nike’s website so that we could demonstrate our tool. The chat tool uses langchains pinecone integration API to convert the user’s chat into an embedding and then do a similarity search in Pinecone.

- Step 4: Generate response to user chat by using langchain to chain together pinecone query search with OpenAI response generation. Test different system messages to pass to OpenAI to find the most optimal.

## Challenges we ran into
- Image Retrieval from Nike: While web scraping Nike's data using Python, we faced an issue retrieving images. They were only available in base64 format, which couldn't be directly converted. We used Selenium to overcome this limitation and retrieve images successfully, but were restricted to gathering data for around 100 items.

- Text Repetition in Chat Responses: Our chat responses sometimes lacked diversity and were repetitive. To improve quality, we utilized OpenAI. By feeding generated text back to OpenAI, we achieved more varied and engaging conversational experiences for users.

- Integrating Backend Pinecone+Generation with Frontend: We used Node.js for easier backend and frontend integration. However, Langchain and Pinecone posed challenges in Node.js. We couldn't integrate some separately developed Python backend code into the frontend.


## Accomplishments that we're proud of
Using a combination of LangChain, OpenAI, Pinecone to recommend shoes that best fit ambiguos customers queries wihtout needing exact matching Creating an AI that sells products to customers with the same care, thought, and diligence as the best store associates

## What we learned
Multiple lang chain functionalities; different ways to connect database to generation How retrieval works in vector databases How associating metadata to the vectors can help AI generate more accurate responses Prompt engineering, we had to experiment with system messages a lot to generate the desired response

## What's next for Yonder Search
Deploy our landing page and Nike demo to a public website If Nike or other shoe companies show interest, we can work with them to customize the knowledge base of our product on their entire catalog and fine-tune our AI to make our responses more concise and include pricing, shipping details, an overall rating, and other promotional information Otherwise, we'll implement our product into local e-commerces like wine.com, mikesbikes.com, and clifbar.com

In the next couple of months, Google will roll out Bard, which will allow NLP-based search for products and services across the web. Over time, large companies like Walmart will have their own NLP-based search solution for their own website. We intend to target vendors that have catalogs of over 10 products that could seriously benefit from NLP-based search but don't have the resources to develop their own solution.

## Images
![landing](./resources/home.png)
![image](./resources/search1.png)

- YouTube Demo: https://youtu.be/yqj3TAietYE


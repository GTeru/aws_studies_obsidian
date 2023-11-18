Cross Origin Resource Sharing (CORS) is a web browser based machanism to allow request to other origins while visiting a main origin

- Origin = schema (protocol) + host (domain) + port
	- E.g.: https://www.example.com (implied port 443 for HTTTPS)

- The request won't be fulfilled unless other origin allows for the requests, using CORS Headers (e.g.: `Access-Control-Allow-Origin`)

## [[S3]] and CORS
---
- If a client makes a cross-origin request to S3, we need to enable the correct CORS headers
- It's a popular exam question
- You can allow for a specific origin or for all origins (using `*`)

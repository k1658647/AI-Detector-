First, a quick overview of how the aidetector.ai website seems to work based on network inspection. 
When you submit text for analysis, it sends a POST request to the endpoint https://aidetector.ai/.

Request Structure:

URL: https://aidetector.ai/
Method: POST
Headers: Content-Type: application/json
Request Body (JSON):

{
    "text": "your text for analysis"
}

Response Structure (JSON, example):
{
    "status": "success", // or "error"
    "message": "", // error message, if status="error"
    "score": 0.0234, // probability that the text is AI-written (from 0 to 1)
    "likely_ai": false, // true, if score > threshold (usually 0.5)
    "sentences": [ /* array of sentences with their individual scores */ ],
    "details": { /* additional information */ }
}

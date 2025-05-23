# AI Agent Plan: Japanese Anime Daily Posts on Xiaohongshu

## Goal

To automate the creation and posting of Japanese anime content on Xiaohongshu, triggered by Telegram, with an email review and approval process.

## Workflow

1.  **Telegram Input:** User sends Japanese anime name via Telegram.
2.  **Information Gathering:** Agent searches Xiaohongshu for relevant content and finds related images online.
3.  **Content Generation:** Agent generates a 100-300 character Chinese post and selects up to 5 images.
4.  **Email Review:** Agent sends the post to a designated email for human review and approval.
5.  **Xiaohongshu Posting:** Upon approval, the agent automatically posts the content to Xiaohongshu.

## Functional Blocks and Components

*   **Input Handling (Telegram):**
    *   Telegram Bot (listens for messages, extracts anime name).
*   **Information Gathering (Xiaohongshu & Internet):**
    *   Xiaohongshu Search/Scraping Module (accesses Xiaohongshu content).
    *   Internet Image Search Module (finds relevant images).
    *   NLP Component (analyzes Xiaohongshu text for themes/keywords).
*   **Content Generation (Text & Images):**
    *   Large Language Model (LLM) (generates Chinese post text).
    *   Image Selection Logic (chooses best images).
    *   Post Formatting Module (combines text and images).
*   **Review Process (Email & Approval):**
    *   Email Sending Module (sends post for review).
    *   Approval Mechanism (email parsing or web interface).
    *   Workflow Management (tracks post status).
*   **Posting (Xiaohongshu):**
    *   Xiaohongshu Posting Module (publish.githubusercontent.comes approved content).

## AI Components and Prompts

*   **Large Language Model (LLM):** Used for generating the post text.
    *   **Prompt Example:** "Generate a Xiaohongshu post about the anime [anime name]. The post should be between 100 and 300 characters in Chinese. Based on the following information from Xiaohongshu discussions: [summarized themes and keywords], write the post in a normal and engaging tone for the platform. Include popular hashtags related to the anime."
*   **NLP Component:** Used for analyzing Xiaohongshu text to identify themes and keywords (internal processing, no direct prompt from the user).
*   **Image Selection Logic:** Internal logic to rank and choose images (no prompt).
*   **Optional Image Generation Model:** Could be used to generate images based on the anime (requires separate prompts based on anime name/scenes).

## Key Features

*   Telegram integration for triggering posts.
*   Xiaohongshu content analysis.
*   AI-powered text generation tailored for Xiaohongshu.
*   Automated image search and selection.
*   Email-based review and approval workflow.
*   Automated posting to Xiaohongshu.
*   (Optional) Input validation, error handling, logging, image generation, performance feedback loop.

## Phased Execution Plan

1.  **Phase 1 (Core):** Telegram input, basic web search, LLM text generation, email sending for manual review/posting.
2.  **Phase 2 (Enhancement):** Implement Xiaohongshu information gathering (scraping/unofficial API), develop NLP for text analysis, refine LLM prompt, integrate image search and selection, improve email content.
3.  **Phase 3 (Automation):** Implement automated email approval or a web interface, develop workflow management, implement Xiaohongshu posting module, connect approval to posting.
4.  **Phase 4 (Advanced):** Add robust error handling/logging, input validation, explore image generation, implement performance feedback loop.

## Potential Challenges

*   Accessing Xiaohongshu data programmatically (scraping is fragile, unofficial APIs carry risks).
*   Maintaining the desired tone and character count with the LLM.
*   Accurate image search and selection for relevance and quality.
*   Handling potential changes in Telegram or Xiaohongshu platforms.
*   Setting up and managing the email review and approval system.

This plan provides a detailed roadmap for developing the AI agent. Prioritize tackling the challenges related to accessing Xiaohongshu data early in the development process. 


## User Rules

Users will interact with the AI agent primarily through a designated Telegram bot. To request a post about a Japanese anime, the user should send a message containing the name of the anime. 

*   **Valid Input:** The core of the message should be the Japanese anime name. Additional text can be included, but the agent will focus on identifying the anime title.
*   **Example:** "Please create a post about [Anime Name] for Xiaohongshu." or simply "[Anime Name]"
*   **Confirmation:** The agent will ideally provide a confirmation message in Telegram once the request is received and processing begins.
*   **Status Updates:** Users will be notified via email about the review status (sent for review, approved, rejected). Final posting confirmation can also be sent via email or potentially back through Telegram.


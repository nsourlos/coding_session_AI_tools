
# Tools and Libraries

### 1.Cursor

1) Normal chat window with `command + l` (`Ctrl + l` on windows)
2) Inline editing with `command + k` (`Ctrl + k` on windows)
   - Create a table for the pricing of o1 preview models mentioned in @Web @https://openai.com/api/pricing/
   - Return a list of bullet points of the main skills a researcher should know based on the information in @Web @https://tu-delft-dcc.github.io/docs/resources/curriculum.html . Return that information exactly as mentioned on the website.
   - Create functions to add, subtract, multiply, and divide two numbers (Explain that if a variable changed in one line, changes will be suggested in all occurrences of that variable in the code)
   - Same for Markdown - better than Word
3) Composer with `command + i` (`Ctrl + i` on windows)
   - Create an test.py file in the Desktop and fill it in with functions to add, subtract, multiply, and divide two numbers - Works in Mac OS
   

### 2.Notebook LM

- Create Q&A pairs and/or multiple choice questions for teaching lessons
- Use it to read a scientific paper, regulatory procedures, legal documents, etc.
- Add notes within it
- Multiple pdfs (up to 50)
- Podcast is the killer feature
   - Can focus on a specific source/topic, target a specific audience
   - Option to share it with others


### 3.Perplexity AI

> Plot the population growth of the Netherlands over the last 10 years

> Pricing of all anthropic vs openai models as table 
    
- In Google some results shown on second page and not as combined table.
- With ChatGPT even if online search is performed, there is no way to find the exact sources and verify its results (this changed early November 2024 though).

In general very good for scientific research and answering questions based on sources - Google just gives 'highlights'
> Is marijuana safe?

> Why llama 3.2 vision is not available in eu?

#### Failure Cases

> Grand Santerson 3blue1brown age 

> Study by Shi et al 2023 detection of bubble clusters

Google works in the second case.

#### Limitations over Google 

Based on Aravind Srinivas - CEO of Perplexity (Post on X on 16 October 2024), Google better among others in: 

- Latency
- Image search
- Specific Queries (e.g. dentists near me) 
- Live updates (e.g sports)
- Shopping

> Note: They are currently working in addressing these. The pro version uses code interpreter to obtain results and can even plot them (like ChatGPT).





### 4.AI Web Scraping (Tutorial in notebook)

<img src="websites_images_videos/DCC_guides_QR.png" alt="Description of image" style="width:40%; height:auto; display:block; margin-left:auto; margin-right:auto;">

1) ***[ScrapeGraph](https://github.com/ScrapeGraphAI/Scrapegraph-ai)***:

   - Easy to use
   - Possible to extract information in a structured way (e.g. json file with some fields filled in)
   - Can use gpt4o-mini for reduced costs

2) ***[Jina](https://jina.ai/)***:
   - Most straightforward tool
   - Use `r.jina.ai` to read a URL:
      - This will return the main content of the page in clean, LLM-friendly text.
   - Use `s.jina.ai` to search a query: 
      - This searches the web and returns URLs and contents, each in clean, LLM-friendly text.
   - Use `g.jina.ai` for grounding: 
      - This will call an underlying grounding engine to do fact-checking (Experimental feature)
   - 1M tokens for free

3) ***[Crawl4ai](https://github.com/unclecode/crawl4ai)***
   - Free, could be used for scraping pages when there is a precictable pattern in the urls (e.g. finish with '/page/1', '/page/2', etc.)
   - Manual extraction of information is needed (some specific fields might be easy to identify - 'Welcome to DCC guides' can be extracted from difference in font size)

4) ***[Firecrawl](https://github.com/mendableai/firecrawl)***

   - The best tool, extracts pages and also all the links in them
   - Limit of 500 pages free, 16$ for 3k pages

5) ***[Screenshot to code](https://github.com/abi/screenshot-to-code)***
   
   - Just take a small video of the website and some pages within it and copy it within a few minutes without access to the code
   - Expensive (~1.5$ for a html page (with images ~+0.3$) - DCC guides created from a 6-7 secs video, and HuggingFace page from a 16sec video, creation took 7mins)

   <video width="640" height="360" controls>
     <source src="websites_images_videos/HuggingFace_page.mp4" type="video/mp4">
   </video>

   **[Example Rendering 1: DCC Guides page](./websites_images_videos/DCC_guides_page.html)**

   **[Example Rendering 2: HuggingFace page](./websites_images_videos/HuggingFace_page.html)**

   Installation instructions [here](./Screenshot_to_code.txt)

### 5.Other tools

1) ***[Vision Agent](https://github.com/landing-ai/vision-agent)***
   - Given an image, it generates code to solve a problem and executes that code
   - Better results than gpt4o
   - Can use open-source models (based on Ollama)

   ```
   from vision_agent.agent import VisionAgentCoder
   agent = VisionAgentCoder()
   code = agent("What percentage of the area of the jar is filled with coffee beans?", media="jar.jpg")
   ```

2) ***[Agent Zero](https://github.com/frdel/agent-zero)***

   - General purpose assistant that writes and executes code
   - It can search the web, and can create tools on-the-fly
   - Fully transparent with the thought process, no limit on what it can do (even delete files - use only within Docker environment)

3) ***[GPT Researcher](https://github.com/assafelovic/gpt-researcher)***

   - Perform scientific research to answer a question
   - Average of 2mins to get a result and costs approx. 0.005$ (for me its was 1min and 0.15$)
   - A similar tool that was recently released by Stanford researchers is [STORM](https://storm.genie.stanford.edu/).

4) ***[AI Renamer](https://github.com/ozgrozer/ai-renamer)*** and ***[Local File Organizer](https://github.com/QiuYannnn/Local-File-Organizer)***
   - Rename files based on their content using both open-sourced and proprietary models (only AI renamer)
   - Supported formats: images, text files, spreadsheets, presentations, pdfs
      - videos, code only by AI Renamer

5) ***[Open Interpreter](https://github.com/OpenInterpreter/open-interpreter)*** 

   A tool that allows us to automatically perform tasks in the computer. Examples are:
   - Control browser to perform a task
   - Plot, clean, and analyze large datasets
   - Create and edit photos, videos, PDFs, etc.

   It asks for approval before performing a task. Video with a demo is available in the repo.

   A similar tool is ***[OS Copilot](https://github.com/OS-Copilot/OS-Copilot)***
   - An attempt to automatically operate the OS
   - Not very good yet, but highly likely to be the way to go in the future
   - Cheap (basic tasks with <0.01$) 

   This might be the future of using OS. Microsoft also recently released [OmniParser](https://github.com/microsoft/OmniParser/blob/master/demo.ipynb), a tool that can parse screenshots of OS and extract information to be used by vision-based agents. 

6) ***[Wispr Flow](https://github.com/wispr-ai/wispr-flow)***
   - Automatic dictation in Mac OS.
   - Can even write simple code
   - Easy to use, just keep `Space` pressed

7) ***[Project Gameface](https://github.com/google/project-gameface)***
   - Use of computer with facial expressions

8) ***[Manim](https://github.com/3b1b/manim)***
   - 3blue1brown animation

## DeepFakes and AI QR Codes

<div style="display: flex; justify-content: space-between;">
    <div>
        <p>Deepfakes Repository</p>
        <img src="websites_images_videos/DeepFakes_Colab.png" alt="Description of image" style="width:90%; height:auto;">
    </div>
    <div>
        <p>AI QR Codes Repository</p>
        <img src="websites_images_videos/QR_codes_Colab.png" alt="Description of image" style="width:90%; height:auto;">
    </div>
</div>
# **Autogen Multi-Agent Framework: Customizable AI Teams for Any Use Case**

This repository demonstrates how to create **custom multi-agent systems** using **Autogen**. These agents can interact, collaborate, and solve tasks such as **document retrieval**, **code generation**, **image generation**, and **video generation**. The system is highly flexible, allowing you to create specialized teams for a variety of tasks, including **DevOps**, **creative content generation**, **AI-driven writing teams**, and more. You can easily swap models for specific use cases such as text, image, or video processing, depending on your project’s requirements.

## **Table of Contents**
1. [Overview](#overview)
2. [Features](#features)
3. [Setup Instructions](#setup-instructions)
4. [Usage](#usage)
    - [Creating Agents](#creating-agents)
    - [Running Conversations](#running-conversations)
5. [Image and Video Generation](#image-and-video-generation)
6. [Customization](#customization)
7. [Use Cases](#use-cases)
8. [Future Enhancements](#future-enhancements)
9. [Contributing](#contributing)
10. [License](#license)

## **Overview**

This project leverages **Autogen** to build highly customizable **AI agents** that can collaborate on tasks, including **document retrieval**, **code generation**, and **retrieval-augmented generation (RAG)** processes. The agents can also be configured to generate images and videos using models like **DALL-E 3**, **RunwayML**, or any other image/video generation model.

In addition to text-based tasks, this framework allows for the creation of AI-driven teams that can handle a wide variety of tasks, including but not limited to:
- **DevOps automation**: Build a team of agents to manage deployments and system monitoring.
- **Creative content generation**: Agents can create images, videos, and written content for social media, blogs, and other marketing purposes.
- **AI-driven writing teams**: Use agents to automate content creation such as articles, scripts, and marketing content.
  
The adaptability of this framework enables you to swap in different models and use cases as needed.

## **Features**
- **Conversational Agents**: Multi-agent systems that can collaborate and solve tasks through conversations.
- **Retrieval-Augmented Generation (RAG)**: Integrate document retrieval capabilities, enhancing the agent's ability to handle complex queries.
- **Image & Video Generation**: Create visual content using **DALL-E 3**, **RunwayML**, or other models.
- **Customizable Agent Configurations**: Easily set up agents for DevOps, creative tasks, code generation, and more.
- **Code Execution Capabilities**: Agents can generate, run, and debug code collaboratively.
- **Flexible Model Integrations**: Support for multiple LLMs and image/video models, including **GPT-4o**, **DALL-E 3**, and others.

## **Setup Instructions**

### **Prerequisites**
- **Python 3.8+**
- **OpenAI API Key** (for LLM and embedding functions)
- **Autogen** (install via pip)
- **Chroma** (for vector storage and document retrieval)
- **Docker** (optional, if using Docker-based agents)

### **Installation**
1. Clone this repository:
   ```bash
   git clone https://github.com/naman1618/autogen-multi-agent-system.git
   cd autogen-multi-agent-system
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your environment variables:
   ```bash
   export OPENAI_API_KEY="your-api-key-here"
   ```

## **Usage**

### **Creating Agents**
The provided scripts allow you to create a range of agents that can handle various tasks. For instance, the `boss` agent acts as a task assigner, while the `coder` agent generates Python code. You can also configure specialized agents for **content creation**, **code review**, or **DevOps tasks**.

```python
# Create a content generation agent
from autogen import AssistantAgent

content_gen_agent = AssistantAgent(
    name="Content_Generator",
    system_message="You are a creative content generator, focused on creating engaging content for blogs and social media."
)
```

### **Running Conversations**
You can initiate conversations between agents using the provided functions like `norag_chat()` or `rag_chat()`:

```python
from your_script import norag_chat, rag_chat

norag_chat()  # Start a basic conversation
rag_chat()    # Start a retrieval-augmented conversation
```

### **Image and Video Generation**

This framework supports **image** and **video generation** through models like **DALL-E 3** or other models, enabling agents to produce creative outputs like images or videos. You can easily integrate these capabilities by updating the **OAI config list**.

#### **Adding DALL-E 3 to the OAI Config List**
To add **DALL-E 3** or any other image generation model, update your configuration file (`OAI_CONFIG_LIST`) as follows:

```json
{
    "models": [
        {
            "model": "gpt-4o",
            "api_key": "your_gpt4_api_key"
        },
        {
            "model": "dall-e-3",
            "api_key": "your_dalle3_api_key"
        }
    ]
}
```

This allows the system to use **DALL-E 3** for **image generation**. Similarly, you can add other models for video generation, such as **RunwayML**.

#### **Using Image Generation with Agents**
Once the model is included in the configuration, you can write agents to generate images based on a given prompt:

```python
from openai import Image

def generate_image(prompt):
    response = Image.create(prompt=prompt, model="dall-e-3")
    return response["data"][0]["url"]

def image_generation_agent(description):
    return generate_image(description)
```

#### **Using Video Generation**
For video generation, you can integrate video models like **RunwayML** or other available tools:

```python
def generate_video(prompt):
    # Example function for video generation using RunwayML API
    response = RunwayML.create_video(prompt=prompt)
    return response["video_url"]

def video_generation_agent(description):
    return generate_video(description)
```

This allows agents to generate creative video content based on prompts, extending their capabilities beyond text-based tasks.

## **Customization**

The agents are highly customizable, and depending on the use case, you can configure them for:
- **DevOps Tasks**: Automate infrastructure deployments and system monitoring.
- **Creative Content Generation**: Use agents to generate images, videos, and written content.
- **Marketing & Writing Teams**: Create blog posts, social media content, and marketing strategies.

### **Model Flexibility**
To switch between different models for **text**, **image**, or **video tasks**, simply modify the `OAI_CONFIG_LIST` file with the desired model configurations.

## **Use Cases**

1. **Creative Teams**: Generate images, videos, and text content for marketing or social media.
2. **DevOps Automation**: Automate CI/CD pipelines, system monitoring, and infrastructure management.
3. **Marketing & Writing Teams**: Use agents to create marketing content, segment customers, and plan campaigns.
4. **Software Engineering Teams**: Automate code reviews, debugging, and collaborative code generation.

## **Future Enhancements**
1. **Integrating More Models**: Add support for additional models for video generation, reinforcement learning, etc.
2. **Improved Context Handling**: Enhance memory functions to improve long-term context retention across agent conversations.
3. **Dynamic Agent Roles**: Allow agents to switch roles based on project requirements in real-time.

## **Contributing**
Feel free to open an issue or submit a pull request if you have ideas for improving this project. Contributions are always welcome!

## **License**
This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

This **README.md** gives a comprehensive explanation of the system, including how to integrate **image and video generation** using **DALL-E 3** or similar models, while keeping the flexibility for various use cases like **DevOps** and **creative teams**. Let me know if you'd like any further adjustments!

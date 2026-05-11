<div align="center">

# 🤖 Voice Agent n8n

### AI Clinic Receptionist Workflow

An intelligent n8n automation workflow that acts as an AI-powered receptionist for a clinic — handling appointment bookings, fetching clinic info, and responding to patients automatically.

[![n8n](https://img.shields.io/badge/n8n-Workflow-EA4B71?style=flat&logo=n8n&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/AI-Powered-412991?style=flat&logo=openai&logoColor=white)](https://openai.com/)
[![Google Calendar](https://img.shields.io/badge/Google%20Calendar-Integration-4285F4?style=flat&logo=googlecalendar&logoColor=white)](https://calendar.google.com/)
[![Google Sheets](https://img.shields.io/badge/Google%20Sheets-Integration-34A853?style=flat&logo=googlesheets&logoColor=white)](https://sheets.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

---

## 📖 Overview

**Voice Agent n8n** is a no-code/low-code AI receptionist workflow built on [n8n](https://n8n.io/). When a patient sends a message via webhook, the AI agent:

1. Understands the patient's request using a language model
2. 2. Fetches up-to-date clinic information from a **Google Sheet**
   3. 3. Books appointments directly into **Google Calendar** if the required details are provided
      4. 4. Sends an automated, contextual response back to the user
        
         5. This workflow eliminates the need for manual front-desk responses and can be integrated with any messaging platform that supports webhooks (WhatsApp, SMS, website chatbots, etc.).
        
         6. ---
        
         7. ## ✨ Features
        
         8. - 📥 **Webhook Trigger** — Receives incoming patient messages from any platform
            - - 🧠 **AI Understanding** — Language model parses intent, extracts appointment details
              - - 📋 **Google Sheets Lookup** — Fetches live clinic hours, services, and doctor availability
                - - 📅 **Google Calendar Booking** — Creates appointments automatically when all details are provided
                  - - 💬 **Auto-Response** — Sends a natural language reply back to the patient
                    - - 🔁 **Fully Automated** — Zero manual intervention required once configured
                     
                      - ---

                      ## 🗂️ Workflow Architecture

                      ```
                      Incoming Message (Webhook)
                              ↓
                        AI Agent (LLM)
                         ↙         ↘
                      Google Sheets  Google Calendar
                      (Fetch Info)   (Book Appointment)
                              ↓
                        Send Response (Webhook / API)
                      ```

                      ---

                      ## 🛠️ Tools & Integrations

                      | Component | Technology |
                      |---|---|
                      | **Automation Platform** | n8n (self-hosted or cloud) |
                      | **AI / LLM** | OpenAI GPT (or compatible model) |
                      | **Clinic Data** | Google Sheets |
                      | **Appointment Booking** | Google Calendar |
                      | **Trigger** | Webhook (HTTP POST) |

                      ---

                      ## 🚀 Getting Started

                      ### Prerequisites

                      - [n8n](https://n8n.io/) instance (self-hosted or n8n Cloud)
                      - - Google account with access to Google Sheets and Google Calendar
                        - - OpenAI API key (or compatible LLM provider)
                         
                          - ### Setup Instructions
                         
                          - 1. **Import the workflow**
                           
                            2.    In your n8n instance, go to **Workflows → Import** and upload the `Working voice agent.json` file from this repository.
                           
                            3.2. **Configure credentials**

                               Set up the following credentials in n8n:

                               - **OpenAI** — Add your OpenAI API key
                               -    - **Google OAuth2** — Connect your Google account for Sheets and Calendar access
                                
                                    - 3. **Set up Google Sheet**
                                     
                                      4.    Create a Google Sheet with your clinic's information (hours, services, doctors). Update the Google Sheets node in the workflow with your Sheet ID.
                                     
                                      5.4. **Set up Google Calendar**

                                         Create or select the Google Calendar where appointments should be booked. Update the Google Calendar node with your Calendar ID.

                                      5. **Activate the webhook**
                                     
                                      6.    Activate the workflow in n8n. Copy the webhook URL generated and connect it to your messaging platform or chatbot.
                                     
                                      7.6. **Test the workflow**

                                         Send a test message to the webhook URL using a tool like Postman or curl:

                                         ```bash
                                            curl -X POST https://your-n8n-instance.com/webhook/your-webhook-id \
                                              -H "Content-Type: application/json" \
                                              -d '{"message": "I would like to book an appointment for tomorrow at 10am"}'
                                            ```

                                         ---

                                         ## ⚠️ Security Notes

                                         - Never expose your webhook URL publicly without authentication
                                         - Store all API keys securely as n8n credentials — never hardcode them in workflow nodes
                                         - Restrict Google OAuth scopes to only what is needed (Sheets read, Calendar write)

                                         ---

                                         ## 🤝 Contributing

                                         Contributions, ideas, and improvements are welcome! Feel free to open an issue or submit a pull request.

                                         ---

                                         ## 📄 License

                                         This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

                                         ---

                                         <div align="center">
                                           Built with ❤️ for smarter clinic automation
                                         </div>

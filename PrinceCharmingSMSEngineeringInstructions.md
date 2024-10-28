## Prince Charming SMS Engineering Integration Blueprint

### **Overview**
The objective of the Prince Charming SMS Engineering system is to re-engage dormant leads, personalize interactions, and guide them toward conversion using an automated, conversational SMS assistant. Integrating GoHighLevel, Zapier, and OpenAI enables real-time data syncing, seamless CRM management, and conversational AI responses, making the lead engagement process efficient and effective.

---

### **1. Technology Integrations**

#### **GoHighLevel Setup**
1. **Account Access**: Ensure you have **Admin** access to the GoHighLevel account to configure settings and integrations.
   
2. **API Key Generation**:
   - Go to **Settings > API Keys** within GoHighLevel.
   - Click **Generate API Key**. Name it (e.g., “Zapier Integration”) and click **Save**.
   - **Copy** the API key. You will use this key in Zapier for data syncing.

3. **Custom Fields and Tagging**:
   - Navigate to **Settings > Custom Fields**.
   - Create fields that will store information needed for SMS personalization, such as:
     - **Lead Status** (e.g., Warm, Cold, Interested)
     - **Last Engagement Date**
     - **Appointment Scheduled** (Yes/No)
   - Set up **Tags** for quick identification and segmentation. Go to **Contacts > Tags** and create tags like “Prince Charming Lead,” “Cold Lead,” and “Booked Meeting.”
   
4. **Automated SMS Messaging Setup**:
   - Go to **Automation** and create a new workflow specifically for Prince Charming SMS.
   - **Trigger**: Set the trigger to **Lead Status Change** or **New Contact Added**, depending on when you want to start the SMS sequence.
   - **Actions**:
     - **Send SMS**: Draft an introductory SMS message inviting the lead to engage with the Prince Charming assistant.
     - **Update Field/Tag**: After the SMS is sent, update the lead status or apply a specific tag to track interaction.

5. **Scheduling Automation for “Coffee Date” Meetings**:
   - Under **Calendar** settings, set up a “Coffee Date” calendar for leads who wish to schedule a Zoom meeting.
   - Link this calendar to GoHighLevel workflows that prompt scheduling when a lead expresses interest in a personalized demo.

#### **Zapier Setup**

1. **Connect GoHighLevel to Zapier**:
   - In Zapier, select **Create a New Zap** and choose GoHighLevel as the **Trigger App**.
   - **Trigger Event**: Select events like **New Lead**, **Tag Added**, or **Contact Updated** to automate actions whenever a lead engages or is updated in GoHighLevel.
   - **Connect Account**: Paste the GoHighLevel API key generated in the earlier steps.

2. **Zapier Workflow Configuration**:
   - **Trigger**: Choose GoHighLevel as the trigger app and set up specific triggers based on lead status updates or engagement.
   - **Actions**:
     - **Filter**: Use Zapier’s Filter tool to continue the Zap only for leads with tags like “Cold Lead” or “Prince Charming Lead.”
     - **Send to OpenAI**: Choose **OpenAI** as the action app. Configure OpenAI to generate conversational SMS messages based on the lead’s information (e.g., industry, previous engagement) pulled from GoHighLevel.

3. **Error Handling**:
   - Configure **Zapier Error Notifications** (under **Zap Settings** > **Error Handling**) to notify you if a Zap fails.
   - Add a **Path** in the workflow for alternative follow-up if a message fails, ensuring continuity in the lead’s engagement.

#### **OpenAI Setup**

1. **Account and API Key Setup**:
   - Go to OpenAI and sign in. Navigate to **API Settings** and generate a new API key. Name it (e.g., “Zapier Integration Key”) for clarity and copy the key.

2. **Prompt Engineering for Prince Charming SMS**:
   - Define the conversational style, tone, and objective:
     - **Introduction Prompt**: “Hi, this is Sarah, Eddie’s digital assistant. Eddie would love to share a tailored solution to boost your lead engagement. Interested?”
     - **Follow-Up Prompts**: Generate specific follow-ups based on the lead’s responses and tag status.
     - **Demo Invitation Prompt**: Invite the lead to a one-on-one Zoom meeting if engagement appears high.
   
3. **Zapier OpenAI Action Configuration**:
   - **Action Event**: Choose **Create Completion** in OpenAI within Zapier to generate responses.
   - **Prompt Input**: Structure the prompt dynamically, pulling in lead data fields from GoHighLevel (e.g., first name, last engagement date).
   - Set the **Temperature** and **Max Tokens** parameters to control response style and length (e.g., **Temperature: 0.7**, **Max Tokens: 50** for concise yet engaging responses).

---

### **2. Granular Configuration Details**

#### **Detailed GoHighLevel Configurations**

1. **Setting Up Contact Record Updates**:
   - Go to **Contacts**, select a contact, and view options for **Adding Custom Fields** (e.g., “Lead Source,” “Last Interaction”).
   - Update these fields automatically via workflows when a lead responds to an SMS or books a meeting.

2. **Tagging System and Status Triggers**:
   - Use tags to denote engagement levels:
     - **“Prince Charming Lead”** for engaged leads.
     - **“Cold Lead”** for leads requiring a bump message.
   - Enable automated tag updates based on lead responses, ensuring Zapier can recognize trigger points for additional follow-up.

#### **Zapier Workflow Configuration Example**

1. **Workflow Example**: Triggered on a GoHighLevel **New Contact Added** event.
   - **Action**: If lead is tagged “Cold Lead,” OpenAI sends a re-engagement SMS.
   - **Conditions**:
     - If **Tag = Cold Lead**: Send initial SMS.
     - If **No Response**: Wait 48 hours, then trigger a follow-up SMS.

2. **Zap Error Handling**:
   - Set **Zap Retry** to attempt re-sending if an error occurs.
   - Configure **Alert Notifications** to notify the admin team if multiple errors are detected in SMS deliveries.

---

### **3. Final Deployment and Testing**

1. **System Testing**:
   - Perform a **GoHighLevel Contact Test** by adding a new lead tagged “Prince Charming Lead.”
   - Ensure Zapier workflows trigger successfully, with OpenAI generating and sending an introductory SMS.
   
2. **Verify Data Flow and Syncing**:
   - Confirm contact information updates across platforms (e.g., if GoHighLevel updates the engagement level, Zapier triggers OpenAI response).
   - Schedule a “Coffee Date” as a test to check GoHighLevel’s calendar and reminder functions.

3. **Troubleshooting Tips**:
   - **SMS Delivery Issues**: Confirm OpenAI’s API key permissions and ensure the Zapier account isn’t over the task limit.
   - **API Key Errors**: Verify that GoHighLevel, Zapier, and OpenAI API keys are up-to-date and re-enter them if necessary.
   - **CRM Sync Errors**: Double-check CRM field mapping in Zapier to ensure data syncing.

---

### **Summary Configuration Example**

- **GoHighLevel**: Configure tags, fields, and workflows for SMS automation and meeting scheduling.
- **Zapier**: Build workflows with GoHighLevel triggers, OpenAI actions, and conditional follow-ups.
- **OpenAI**: Craft conversational prompts to engage leads through SMS, guiding them to personalized demos or meetings.

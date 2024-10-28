# Knowledgebase Article: Using Tags in GoHighLevel for Automated Workflows

---

## Table of Contents

1. **Overview**
2. **Workflow Trigger - Contact Tag**
   - Trigger Name
   - Trigger Description
   - How to Configure
   - Example: Personalized Follow-Up Workflow

---

### 1. Overview

In GoHighLevel, **tags** allow you to trigger workflows based on changes in contact tagging. By utilizing the **"Contact Tag"** trigger, you can automate specific actions when a tag is added to or removed from a contact, such as sending follow-up emails, notifying team members, or initiating re-engagement campaigns. Tags are especially helpful for segmenting leads and tailoring customer communications.

---

### 2. Workflow Trigger - Contact Tag

#### **Trigger Name**
**Contact Tag**

#### **Trigger Description**
The **Contact Tag** trigger activates whenever a specified tag is added or removed from a contact, helping automate responses based on customer interest, status changes, or specific actions.

#### **Trigger Details**

| Value               | Description                                               | Mandatory |
|---------------------|-----------------------------------------------------------|-----------|
| Workflow Trigger    | Event that initiates the workflow (select "Contact Tag").  | Yes       |
| Workflow Trigger Name | Custom name for easy identification (e.g., "Interested Tag Updated") | Yes |
| Filters             | Criteria defining which tag addition or removal triggers the workflow (e.g., Tag Added: "interested"). | No |

---

### 3. How to Configure

To set up a **Contact Tag** workflow in GoHighLevel:

1. **Choose a Workflow Trigger:**
   - From the trigger dropdown menu, select **"Contact Tag"**.

2. **Set the Workflow Trigger Name:**
   - Assign a name, such as **"Tag 'Interested' Added or Removed"**, for easy identification in your workflow list.

3. **Configure Filters:**
   - Click on **"Add filters"** to define the criteria for triggering the workflow.
   - Select **Tag Added** from the filter options and specify the tag (e.g., **"interested"**).
   - Optionally, add a second filter for **Tag Removed** with the same tag to automate actions on both adding and removing the tag.

4. **Define Actions for Tag Added:**
   - Specify the actions when the tag is added. For instance:
     - **Send a personalized email** to the tagged contact.
     - **Notify the sales team** to follow up on the new lead interest.

5. **Define Actions for Tag Removed:**
   - Specify the actions when the tag is removed. For example:
     - **Send a re-engagement email** to understand why the interest was removed.
     - **Send a survey** to gather customer feedback for continuous improvement.

---

### 4. Example: Personalized Follow-Up Workflow

**Trigger Setup:**

- **Workflow Trigger**: Contact Tag
- **Workflow Trigger Name**: Tag "Interested" Added or Removed

**Filters:**

- **Tag Added**: "interested"
- **Tag Removed**: "interested"

**Actions for Tag Added:**

- **Action**: Send Email
  - **Email Action Name**: Follow-Up Email for Interested Contacts
  - **From Name**: [Your Company Name]
  - **From Email**: yourcompany@example.com
  - **Subject**: "Thank You for Your Interest!"
  - **Email Body**:
    ```
    Hi {{contact.first_name}},

    Thank you for showing interest in our products/services. We have some exciting offers and updates tailored just for you.

    Please feel free to reach out if you have any questions or need further information.

    Best Regards,  
    [Your Company Name]
    ```

- **Action**: Internal Notification to Sales Rep
  - **Message**: "A contact tagged as 'interested' requires follow-up. Contact details: {{contact.details}}."

**Actions for Tag Removed:**

- **Action**: Re-Engagement Email
  - **From Name**: [Your Company Name]
  - **From Email**: yourcompany@example.com
  - **Subject**: "We Miss You!"
  - **Email Body**:
    ```
    Hi {{contact.first_name}},

    We noticed you have removed your interest tag. We would love to understand why and how we can better serve you.

    Please take a moment to provide us with feedback or let us know if there's anything we can do to assist you.

    Best Regards,  
    [Your Company Name]
    ```

---

### Outcome

This automation ensures that contacts tagged as **"interested"** receive timely, personalized follow-up emails, with notifications to the sales team for further engagement. It also supports re-engagement efforts for contacts who lose interest by prompting them to provide feedback, helping improve customer retention and better understand client needs.

---

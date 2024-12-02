# **Enhancement for LibreChat: Show Token Usage per Conversation**

LibreChat is an open-source chat platform designed to provide a customizable experience for users based on different AI models. I'm working on an enhancement for **LibreChat (Issue #1215)** to show users how much their conversation has cost in terms of API usage. This feature has been requested by many users and has been in the backlog for a while.

The goal is simple: **give users a clear view of how many tokens they used in each chat response**.

---

## **Two Approaches to Implement the Feature**

### **1. Returning Token Cost from Backend (`checkBalance.js`)**

For this approach:
- Modify the backend function (`checkBalance.js`) to calculate and return the `tokenCost`.
- The token cost is included in the API response sent to the frontend.
- Every time a chat response is generated, it will include the token usage information.

#### **Worklist**
- **Update `checkBalance.js`**: Modify the function to calculate and return `tokenCost` along with the ability to spend.
- **API Route Update**: Integrate the updated function and include `tokenCost` in the API response.
- **Frontend Changes**: Update the UI to display the `tokenCost` to users in the chat interface.

#### **Pros**
- Easy to implement and fits well with the current API setup.
- Minimal disruption to existing logic.

#### **Cons**
- Requires backend modifications.
- Ensuring consistency across all API responses may become tricky.

---

### **2. Middleware Approach**

In this approach:
- Introduce middleware to attach the `tokenCost` directly to the request object.
- The token cost will be accessible throughout the lifecycle of the request and can be included in any API response as needed.

#### **How to Do It**
1. **Modify `checkBalance.js`**: Update it to calculate `tokenCost` and attach it to the `req` object.
2. **Add Middleware**: Create middleware to inject `tokenCost` into API responses.
3. **API Integration**: Ensure all relevant API routes can access `req.tokenCost` and include it in their responses.

#### **Pros**
- Centralized token cost calculation logic avoids duplication.
- Flexible and reusable across different API endpoints.

#### **Cons**
- Adds more complexity to the middleware.
- Debugging middleware logic can become challenging.

---

## **What's Next?**

1. **Pick an Approach**: Implement both approaches and evaluate which one fits better with the current setup.
2. **Sync Backend and Frontend**: Ensure the backend API sends token usage information seamlessly, and the frontend displays it effectively.
3. **Thorough Testing**: Test thoroughly to validate the accuracy of token usage information and ensure smooth integration.

---


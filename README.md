This is a proof-of-concept (POC) API project developed collaboratively to enable users to post, manage, and control the lifecycle of classified ads. The API allows users to activate or deactivate their ads at will and perform various operations related to each listing.

Following the feedback from the POC demo, the project may be further developed and turned into a production-ready application. Therefore, the POC is expected to be built at a level that provides a solid foundation for future development. As a bonus, the team may optionally include surprise features in the demo to receive positive feedback.

📋 Classified Ad Fields and Validation Rules
Each classified ad submitted by users must include the following fields and comply with the specified validation rules:

Ad Title
Must start with a letter (Turkish characters allowed) or a digit.

Must be between 10 and 50 characters long.

Entry should be blocked if any word from the Badwords.txt file is present in the title.

Ad Description
Must be between 20 and 200 characters long.

Special characters are allowed.

Ad Category
Must be one of the following: Real Estate, Vehicle, Shopping, Other

(For the POC, no additional categories are planned.)

🔄 Classified Ad Lifecycle & Business Rules
When an ad is first submitted:

If the category is Real Estate, Vehicle, or Other, it is created with a status of Pending Approval.

If the category is Shopping, it is created with a status of Active (no approval required).

Ads with the same category, title, and description are marked as Duplicate and cannot be updated.

A classified ad in Pending Approval can be approved and then moves to Active.

(In this POC, all pending ads are assumed to be approved; rejection scenarios are not considered.)

Users can change the status of their Active or Pending Approval ads to Inactive.

Re-activation of inactive ads is not required to be implemented for this POC.

🛠️ Development Assumptions
Users creating and approving ads can be assumed to be the same person. Authentication is assumed to be present.

Only the status of the ad can be updated. Updating title, description, or category is out of scope.

Re-activating an inactive ad is not required for the demo and does not need to be implemented.

✅ API Scope & Endpoints
The API functionalities that the team has chosen to implement for this POC include:

Create a classified ad

Update ad status (Activate, Deactivate, etc.)

List statistics showing the number of ads by status
GET /dashboard/classifieds/statistics
Example Response: { "Active": 151, "Inactive": 71 }

BONUS: List the full history of status changes for a classified ad over time

🚧 Project Constraints
Java 11

Maven 3.6+

Spring Boot 2+
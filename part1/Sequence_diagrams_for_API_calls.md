**Sequence Diagrams for API Calls in HBnB Application**

## **Overview**
This document provides sequence diagrams for four key API calls in the HBnB application. These diagrams illustrate the interactions between the **Presentation Layer (Services, API), Business Logic Layer (Models), and Persistence Layer (Database)**, demonstrating how requests are processed across the system.

## **API Calls and Sequence Diagrams**

### **1. User Registration**
**Description:** A user submits registration details to create a new account.
[![](https://mermaid.ink/img/pako:eNptUU1rwzAM_SvG55bdfShsK4PBDqVlOwxfVEdNxRI5s-XBKP3vU5JmI2Q-6eM9vSfrYkOs0Dqb8bMgB9wS1Alaz0ZfB0koUAcs5jVjWlbvd8_L4kPJxJjzS6wpLNtbEDhCRs9jr5-83mx0lDOHcmxJzB5rypJAKLImai3LCFaUYmcKzrxBQxUIGuDK7FIM2prTZgQdMHlQRfjCwcLga0RP3fVS6jHyiVI70P4bPS2yRymJdZ_Qm7l7AmpKQi3nLnLGv2WU0Ku7-c43mSGxK9uixlTpnS4901s5Y4veOg0rSB_eer4qDorEwzcH6yQVXNkUS3227gRN1qx0_SfdLvxb1Zu8xzjl1x9I1LZM?type=png)](https://mermaid.live/edit#pako:eNptUU1rwzAM_SvG55bdfShsK4PBDqVlOwxfVEdNxRI5s-XBKP3vU5JmI2Q-6eM9vSfrYkOs0Dqb8bMgB9wS1Alaz0ZfB0koUAcs5jVjWlbvd8_L4kPJxJjzS6wpLNtbEDhCRs9jr5-83mx0lDOHcmxJzB5rypJAKLImai3LCFaUYmcKzrxBQxUIGuDK7FIM2prTZgQdMHlQRfjCwcLga0RP3fVS6jHyiVI70P4bPS2yRymJdZ_Qm7l7AmpKQi3nLnLGv2WU0Ku7-c43mSGxK9uixlTpnS4901s5Y4veOg0rSB_eer4qDorEwzcH6yQVXNkUS3227gRN1qx0_SfdLvxb1Zu8xzjl1x9I1LZM)

### **2. Place Creation**
**Description:** A registered user creates a new place listing.
[![](https://mermaid.ink/img/pako:eNptUctqAzEM_BXjc0LvPgTyoBDoISQ0h-KL4tVuTNfy1o9CCfn3yvtoSbc-SaMZjSXdpPEVSiUjfmQkgzsLTQCnSfDrICRrbAeUxGvEMEfXh_0c3ORoCWN88Y018_IOElwgoqahVjovVytupcQpX5xN4tCCQbENCMl6EsfyuZgGOvOY_eChxBlaW0HCUVksBvYDj3WTOVvB50TfU-2D670G1cRazp22nmobXC__z2Ka5IgpB-KBjOHa0zPYNgdkOHaeIv7OwoKyAfV36NGoT-RCOuTYVnyqW9Fqma7oUEvFYQXhXUtNd-ZBTv70RUaqFDIuZPC5uUpVQxs5y13Z0njkH5TP8ub9lN-_AVfgtmA?type=png)](https://mermaid.live/edit#pako:eNptUctqAzEM_BXjc0LvPgTyoBDoISQ0h-KL4tVuTNfy1o9CCfn3yvtoSbc-SaMZjSXdpPEVSiUjfmQkgzsLTQCnSfDrICRrbAeUxGvEMEfXh_0c3ORoCWN88Y018_IOElwgoqahVjovVytupcQpX5xN4tCCQbENCMl6EsfyuZgGOvOY_eChxBlaW0HCUVksBvYDj3WTOVvB50TfU-2D670G1cRazp22nmobXC__z2Ka5IgpB-KBjOHa0zPYNgdkOHaeIv7OwoKyAfV36NGoT-RCOuTYVnyqW9Fqma7oUEvFYQXhXUtNd-ZBTv70RUaqFDIuZPC5uUpVQxs5y13Z0njkH5TP8ub9lN-_AVfgtmA)

### **3. Review Submission**
**Description:** A user submits a review for a specific place.
[![](https://mermaid.ink/img/pako:eNptUbFqAzEM_RXjOaG7h0DbUCh0CAntUG5RfEoieidfLTulhPx75VzcEq5ebOm9pydZJ-tDi9ZZwc-M7HFJsI_QN2z0DBATeRqAk3kVjNPs_ep5mnzIQowiL2FPfgovIcEWBBsesVJ5vlhoKWc2edtTMms8En7ppU1JGmmKK-umtjNv0FELCQ1wa1YxeIWu6lF1w1d9NVcrOGI1KtmRX_H51Osx8I5ifxH-V7zOsMaUI-sovnRz9wTU5VisZAgs-DeNCsrsrnZxGV6EAlcvSBrYme1R39Tqnk5F3th0wB4b6_TZQvxobMNn5UFOYfPN3roUM85sDHl_sG4HnWiUh_JV1w3_ZnUn7yHU-PwDl1a14g?type=png)](https://mermaid.live/edit#pako:eNptUbFqAzEM_RXjOaG7h0DbUCh0CAntUG5RfEoieidfLTulhPx75VzcEq5ebOm9pydZJ-tDi9ZZwc-M7HFJsI_QN2z0DBATeRqAk3kVjNPs_ep5mnzIQowiL2FPfgovIcEWBBsesVJ5vlhoKWc2edtTMms8En7ppU1JGmmKK-umtjNv0FELCQ1wa1YxeIWu6lF1w1d9NVcrOGI1KtmRX_H51Osx8I5ifxH-V7zOsMaUI-sovnRz9wTU5VisZAgs-DeNCsrsrnZxGV6EAlcvSBrYme1R39Tqnk5F3th0wB4b6_TZQvxobMNn5UFOYfPN3roUM85sDHl_sG4HnWiUh_JV1w3_ZnUn7yHU-PwDl1a14g)

### **4. Fetching a List of Places**
**Description:** A user requests a list of places based on specific criteria.
[![](https://mermaid.ink/img/pako:eNp1kcFqwzAMhl9F-Ny-gA-FdWUw6KBr2WX4otlqYtbYmS0fSum7T26ajZDNB2H9_vTLQhdloyOlVaavQsHSxmOTsDMB5PSY2FvfY2B4y5Tm6sPueS6uS_aBct7Gxtv58wYZPzCTCcNbdV6uVmKlYV-_kRm2XkI8wu6ElvLACSDYxFzDE7Ft4QUl-tBM-AkplWNfDa-F0vnOwlokBzHAY_JMyeNQPdLLec89cUlhqL9xf_X7negG_zeQYHV-DQcK7m5ZWbVQHaUOvZPlXCpvFLfUkVFarg7Tp1EmXIXDwvFwDlZpToUWKsXStEof8ZQlK71DHtf6o8oi3mMc8-s3PCCvlg?type=png)](https://mermaid.live/edit#pako:eNp1kcFqwzAMhl9F-Ny-gA-FdWUw6KBr2WX4otlqYtbYmS0fSum7T26ajZDNB2H9_vTLQhdloyOlVaavQsHSxmOTsDMB5PSY2FvfY2B4y5Tm6sPueS6uS_aBct7Gxtv58wYZPzCTCcNbdV6uVmKlYV-_kRm2XkI8wu6ElvLACSDYxFzDE7Ft4QUl-tBM-AkplWNfDa-F0vnOwlokBzHAY_JMyeNQPdLLec89cUlhqL9xf_X7negG_zeQYHV-DQcK7m5ZWbVQHaUOvZPlXCpvFLfUkVFarg7Tp1EmXIXDwvFwDlZpToUWKsXStEof8ZQlK71DHtf6o8oi3mMc8-s3PCCvlg)

## **Conclusion**
These sequence diagrams provide a clear representation of how the **HBnB** application processes user requests at different layers. The **API interacts with the Business Logic Layer**, which in turn **manages interactions with the Persistence Layer**, ensuring a structured flow of information and data integrity.
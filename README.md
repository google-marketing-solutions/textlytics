# Textlytics: Text Assets Performance Dashboard

Welcome to Textlytics, an Assets Performance Dashboard repository!
This project is dedicated to building a streamlined Looker Studio dashboard that aggregates creative asset performance data from an MCC Google Ads account. The primary focus is on scaling the analysis of text assets, enabling quick insights and informed decision-making.

## Overview

This repository provides a solution to build an automated workflow for pulling Google Ads assets performance data daily into BigQuery. The solution leverages the [gaarf-workflow framework](https://github.com/google/ads-api-report-fetcher), which simplifies the integration between the Google Ads API and BigQuery using Google Cloud services such as Cloud Functions, Workflows, and Cloud Scheduler.

The workflow includes:

1. Defining and configuring SQL-like queries.
2. Automatically running the queries daily to fetch data via the Google Ads API.
3. Transferring and storing the data in BigQuery for scalable analysis.
4. Visualizing the processed data in Looker Studio with a pre-configured dashboard.

**Prerequisites**:

1.  **Google Ads API Developer Token**

    - Access the [Google Ads](https://ads.google.com) platform at the MCC level.
    - Navigate to **Tools & Settings > Setup > API Center**. If you don’t see a developer token, complete the required details and request one.
    - By default, new tokens are granted "Test Account" access. To run Textlytics, you must apply for "Basic" or "Standard" Access by following [these instructions](https://developers.google.com/google-ads/api/docs/access-levels).

2.  **Google Cloud Project**

    - Create a new project in the [Google Cloud Console](https://console.cloud.google.com/).
    - Ensure the project is linked to an active **billing account**.

3.  **Authentication Setup**
    Choose one of the following authentication methods:
    - **OAuth Credentials:** This manual process generates credentials based on a specific user's access to the Google Ads account. Create your `google_ads.yaml` file by following this [step-by-step tutorial](https://console.cloud.google.com/?cloudshell=true&cloudshell_git_repo=https://github.com/google-marketing-solutions/credentials_creator_walkthrough&cloudshell_tutorial=walkthrough.md).
    - **Service Account:** Grant read-only access to your Google Ads MCC (Manager Account) for your project's Default Compute Engine service account. The service account ID is formatted as `[project-number]-compute@developer.gserviceaccount.com`.

## Implementation Guide

Follow these steps to set up your Textlytics dashboard:

1.  **Get Access to the Dashboard Template**

    - To get access to the [Looker Studio dashboard template](https://lookerstudio.google.com/c/u/0/reporting/ed8492be-265f-4e46-9451-1bb53f66593a/page/p_svvezsdpkd), ask your Google representative to add you to the [Textlytics Readers Google Group](https://groups.google.com/a/professional-services.goog/g/solutions_textlytics-readers).

2.  **Open the Cloud Shell**

    - In your Google Cloud project, activate the Cloud Shell by clicking the terminal icon in the top-right corner of the console.

3.  **Download the Project Files**

    - In the Cloud Shell terminal, run the following commands (copy to the terminal and press 'Enter'):
      ```bash
      git clone https://github.com/google-marketing-solutions/textlytics
      ```

4.  **Navigate to the Project Directory**

    - Enter the newly created directory with this command:
      ```bash
      cd textlytics
      ```

5.  **Run the Setup Script**

    - Execute the initialization script and follow the on-screen prompts to configure your project.
      ```bash
      sh init_wf.sh
      ```

6.  **Provide Google Ads Credentials**

    - **For OAuth:** The script will prompt you for the credentials needed to create the `google-ads.yaml` file.
    - **For Service Account:** Before running the script, ensure your Default Compute Engine service account has read permissions for your Google Ads MCC.

7.  **Access Your Dashboard**
    - Once the setup is complete, the script will display a URL for your new Looker Studio dashboard. Click the link to view your text asset performance.

## Contact

For any additional questions or feedback, feel free to contact [halelid@google.com](mailto:halelid@google.com).

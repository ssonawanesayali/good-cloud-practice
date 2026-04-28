<p align="center">
  <img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/logo.png" alt="Logo">
</p>

<p align="center">A python3 script which scans and generates an HTML report regarding Google Cloud Platform non-compliance.</p>

<p align="center">
  <a href="#introduction">Introduction</a>
  | <a href="#main-features">Main Features</a>
  | <a href="#requirements">Requirements</a>
  | <a href="#installation">Installation</a>
  | <a href="#usage">Usage</a>
  | <a href="#examples">Examples</a>
  | <a href="#html-report">HTML report</a>
  | <a href="#contributing">Contributing</a>
  | <a href="#thanks">Thanks</a>
</p>

<div align="center">
  Maintained by <a href="http://www.linkedin.com/in/sonawanesayali/">Sayali Sanjay Sonawane</a>
  <br>
  Originally created by <a href="https://liodeus.github.io/">Liodeus</a>
</div>

## Introduction

This tool is designed to facilitate security assessments and identify non-compliance issues within Google Cloud Platform environments. It serves as a practical utility for auditing cloud infrastructure and improving security posture.

## Main Features

- BigQuery checks : 1
- Cloud DNS checks : 2
- Google AppEngine checks : 4
- Google Compute Engine checks : 13
- Google Cloud Function checks : 4
- Cloud SQL checks : 4
- Google Cloud Storage : 1
- Google Cloud Key Management : 1

## Requirements

You will need to have a Google account and the following tools installed.

### Tools

- [gcloud](https://cloud.google.com/sdk/docs/install#deb)
- python3
- python3-pip

Once gcloud is installed, you need to authorize gcloud to access the Cloud Platform with Google user credentials or use a service account via a key:

#### Authorize gcloud
```bash
gcloud auth login
```

##### Service account

1. In the Cloud Console, go to the Service accounts page.
2. Select a project.
3. Click Create service account.
   Enter a service account name to display in the Cloud Console.
4. The Cloud Console generates a service account ID based on this name. Edit the ID if necessary. You cannot change the ID later.
5. To set access controls, click Create and continue to the next step.
6. Choose one or more IAM roles to grant to the service account on the project.
7. Grant the role : Viewer
8. When you are done adding roles, click Continue.

##### Generate keys

1. Click on your newly created account
2. Go to keys panel
3. Add key -> Create new key
4. Key type : JSON
5. Click create and store the key securely

## Installation

```
git clone https://github.com/Liodeus/Good-Cloud-Practice
cd Good-Cloud-Practice
pip3 install -r requirements.txt
```

## Usage

```
Usage: Good_Cloud_Practice.py [-h] [-r] [-lp] [-lu] [-pi PROJECT_ID] [-l LIST] [-u USER] [-k KEY]

optional arguments:
  -h, --help            show this help message and exit
  -r, --report          Enable report mode
  -lp, --list_projects  List projects
  -lu, --list_users     List users
  -pi PROJECT_ID, --project_id PROJECT_ID
                        Do the compliances checks on this project ID
  -l LIST, --list LIST  Do the compliances checks on this list of project ID
  -u USER, --user USER  Use this user account to do the compliances checks
  -k KEY, --key KEY     Use this service account to do the compliances checks
```

## Examples

Run all the compliance checks on every project:
```shell
python3 Good_Cloud_Practice.py
```

Run all the compliance checks on every project and enable report mode:
```shell
python3 Good_Cloud_Practice.py -r
```

Run all the compliance checks on a particular project:
```shell
python3 Good_Cloud_Practice.py --project_id mystic-sun-309920
```

Use a service account:
```shell
python3 Good_Cloud_Practice.py -k path_of_the_key.json
```

List users:
```shell
python3 Good_Cloud_Practice.py -lu
```

Use a particular account:
```shell
python3 Good_Cloud_Practice.py -u ACCOUNT
```

## HTML report

### Header
Displays the user who launched the scan and the date of the scan.
<img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/header.png" alt="Header">

### Global section
Includes a summary of all non-compliances (only printed if there is more than one project scan).
<img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/global.png" alt="Global">

### Report section
Displays the name of the project scanned, the summary of non-compliances found, and the results.
<img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/section.png" alt="Section">

### Results
Once the "Results" are unfolded, three sections are available.
<img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/unfold_section.png" alt="Unfold section">

### Section
Detailed view of the "Non compliant" section once unfolded.
<img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/unfold_section_two.png" alt="Unfold section two">

### Footer
The footer contains relevant links and a "Back to the top" button.
<img src="https://github.com/Liodeus/Good-Cloud-Practice/blob/main/images/footer.png" alt="Footer">

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss the proposed modifications.

## Thanks

Special thanks to the following project for inspiration: [ram](https://github.com/BrunoReboul/ram).

## About the Maintainer

Sayali Sanjay Sonawane is a CISA-certified Technology Audit and Information Security Risk professional. With over 4 years of experience, she specializes in ITGC assessments, technology risk evaluations, and security control testing across enterprise environments. She focuses on leveraging data analytics and automation to enhance audit quality and security remediation.

**Contact Information:**
- LinkedIn: http://www.linkedin.com/in/sonawanesayali/
- Email: ssonawanesayali@gmail.com
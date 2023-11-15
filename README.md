# helm-repo
# Adding a new repo to a github

## Step 1: Install Helm
If you haven't already installed Helm, you can follow the official Helm installation guide: https://helm.sh/docs/intro/install/.

## Step 2: Initialize a Helm Chart Repository
1. Create a new GitHub repository to store your Helm charts.

Clone the repository to your local machine:

```bash
git clone https://github.com/your-username/your-helm-charts-repo.git
```

## Step 3: Create Your Helm Chart
Create your Helm chart or use an existing one. Ensure that your chart is structured properly with the necessary files, including Chart.yaml, values.yaml, and the template files in the templates directory.

```bash
helm create <chart-name>
```

## Step 4: Package Your Helm Chart
Package your Helm chart into a tarball:

```bash
helm package path/to/your/chart
```

This will create a '**.tgz**' file in your current directory.

## Step 5: Push Your Helm Chart to GitHub

1. Update the Helm repository index:

```bash
helm repo index .
```
Replace "your-username" and "your-helm-charts-repo" with your GitHub username and the name of your github repository.

2. Commit and push the changes to the GitHub repository:

```bash
git add .
git commit -m "message"
git push origin main
```
## Step 6: Use the Helm Chart
Now, you can add your Helm chart repository and install your chart:

```bash
helm repo add your-repo-name https://raw.githubusercontent.com/your-username/your-helm-charts-repo/main

```
Replace "your-username" and "your-helm-charts-repo" with your GitHub username and the name of your github repository.


## step 7: verify if repo was added correctly

```bash
helm repo list 
```

## step 8: Deploy the helm helm chart

```bash
helm search repo <repo-name>  

helm install your-chart-name your-repo-name/your-chart-name
```
Replace "your-repo-name" and "your-chart-name" with the appropriate names.

## Other commands:
- search charts under the repo
```bash
helm search repo <repo-name> 
# popular helm commands

- create a helm chart
```bash
helm create <chart-name>
```
- check helm chart for syntax errors
```bash
helm lint <chart>
```
- show template of all manifest configurations in the helm chart

```bash
helm template <char>t
```
- Deploy a helm chart on the kubernetes cluster
```bash
helm install <release-name> <chart-direcotry>
```

- list all helm releases/deployments
```bash
helm list
```

- Upgrades a release to a new version of a chart or updates its configuration
 
```bash
helm upgrade <release-name> <chart>
```

- show helm default values

```bash
helm show values <chart>
```

- search charts under the repo
```bash
helm search repo <repo-name> 
```

- get history of revision changes to deployment
```bash
helm history <release-name>
```

- rollback revision to a previous revision
```bash
helm rollback <release-name> <revision-number>
```
- uninstall helm release/deployment
```bash
helm uninstall <release-name>
```

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

## step 8: Deploy the helm helm chart. First search the repo to get chart name

```bash
helm search repo <repo-name>  
```
Then install helm chart

```bash
helm install <release-name> <your-repo-name/your-chart-name>
```
Replace "your-repo-name" and "your-chart-name" with the appropriate names.

## step 9: Uninstall chart

```bash
helm uninstall <release-name>
```

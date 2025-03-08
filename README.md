# Story Hour Improv

This is the source for the StoryHourImprov.com website, an interactive musical theater experience for families with children.

This site is built using the [Docsy Theme](https://github.com/google/docsy), a Hugo theme.

## GitHub Pages and Custom Domain Setup

This site is configured to deploy automatically to GitHub Pages using GitHub Actions. When you push to the main branch, the site will be built and deployed to GitHub Pages.

### Setup Instructions

1. **Enable GitHub Pages in your repository settings**:
   - Go to your GitHub repository
   - Navigate to "Settings" > "Pages"
   - Under "Source", select "GitHub Actions" as the source
   - This allows the GitHub Actions workflow to deploy your site

2. **Configure your AWS Route53 domain**:
   - In your AWS Route53 dashboard, create the following DNS records for `storyhourimprov.com`:
     - Type: A
       - Name: @ or storyhourimprov.com
       - Value: 185.199.108.153
       - Value: 185.199.109.153
       - Value: 185.199.110.153
       - Value: 185.199.111.153
       - (These are GitHub Pages' IP addresses)
       - TTL: 300
     - Type: CNAME
       - Name: www
       - Value: your-username.github.io (replace with your GitHub username)
       - TTL: 300

3. **Set custom domain in GitHub Pages**:
   - After the first workflow run completes
   - Go to repository "Settings" > "Pages"
   - In the "Custom domain" field, enter "storyhourimprov.com"
   - Check "Enforce HTTPS" once the SSL certificate is provisioned (may take up to 24 hours)

If you want to do SCSS edits and want to publish these, you need to install `PostCSS`. Navigate to the project root, and call

```bash
npm install postcss
```

## Running the website locally

Building and running the site locally requires a recent `extended` version of [Hugo](https://gohugo.io).
You can find out more about how to install Hugo for your environment in our
[Getting started](https://www.docsy.dev/docs/getting-started/#prerequisites-and-installation) guide.

Once you've made your working copy of the site repo, from the repo root folder, run:

```bash
hugo server
```

## Running a container locally

You can run docsy-example inside a [Docker](https://docs.docker.com/)
container, the container runs with a volume bound to the `docsy-example`
folder. This approach doesn't require you to install any dependencies other
than [Docker Desktop](https://www.docker.com/products/docker-desktop) on
Windows and Mac, and [Docker Compose](https://docs.docker.com/compose/install/)
on Linux.

1. Build the docker image

   ```bash
   docker-compose build
   ```

1. Run the built image

   ```bash
   docker-compose up
   ```

   > NOTE: You can run both commands at once with `docker-compose up --build`.

1. Verify that the service is working.

   Open your web browser and type `http://localhost:1313` in your navigation bar,
   This opens a local instance of the docsy-example homepage. You can now make
   changes to the docsy example and those changes will immediately show up in your
   browser after you save.

### Cleanup

To stop Docker Compose, on your terminal window, press **Ctrl + C**.

To remove the produced images run:

```bash
docker-compose rm
```
For more information see the [Docker Compose documentation][].


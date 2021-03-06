page_main_title: Shippable Server - Install State storage
main_section: Platform
sub_section: Shippable Server
sub_sub_section: Configuration
page_title: Shippable Server - Install State storage
page_description: Install Gitlab for storing state for Shippable Server
page_keywords: ci, continuous integration, devops, docker, on-premises, enterprise, gitlab

# State Storage (Gitlab) Configuration

Shippable Server uses Gitlab to store state, which is any information like a file or key-value pair that is stored by a version of a job or resource and can be retrieved by downstream jobs in your Assembly Line.

You have a few choices of where you want to run your Gitlab server:

* Fresh installation on the same machine as Installer
* Fresh installation on a different machine from the Installer (**Recommended**)
* Use an existing Gitlab server, either from a previous Shippable installation, or your own instance

Our recommended approach is to do a fresh installation on a machine separate from the installer for space and performance reasons. GitLab can easily be installed on a separate supported OS machine with the Admiral installer by configuring the **STATE** section.

<img src="/images/platform/server/admiral-gitlab-config.png" alt="Configuring Gitlab for state store">


## Installing State

When you first log in to the [Admiral UI](/platform/server/install/#the-admiral-ui), GitLab will not yet be installed or initialized. Follow the instructions below, depending on where you want to install GitLab.


### Fresh instance on the same machine

To install Gitlab on the same machine as the one where Admiral is installed, select  **This Node** from the dropdown under `Install State on` in the **STATE** section of the **Control plane** panel in the Admiral UI.

<img src="/images/platform/server/gitlab-this-node.png" alt="Installing Gitlab on the current node">

You will need to click the **Apply** button after completing other sections.

### Fresh instance on a new machine

You can choose to install Gitlab on a separate server from the one where Admiral is installed. This will install GitLab CE version 8.9.6.

<img src="/images/platform/server/gitlab-new-node.png" alt="Installing Gitlab on the current node">

- Select **New Node** from the dropdown under `Install State on` for **STATE** in the **Control plane** panel..
- Enter a password for the root GitLab user.
- Enter the IP address where you would like to install GitLab.  This should be a supported OS machine with ports 80, 443, and 22 accessible to the other Shippable components and services.
- Run the command displayed to allow Admiral SSH access to the machine on the machine chosen and check the box to confirm that this step was completed.  SSH access is required to run the installation scripts.

You will need to click the **Apply** button after completing other sections. Installation progress will be shown on the right side of the Control plane panel.

### Connecting to an existing instance

If you have an existing instance of Gitlab, either left over from a previous Shippable installation or your own instance, you can reuse that with Shippable Server.

To configure this:

<img src="/images/platform/server/gitlab-existing.png" alt="Installing Gitlab on the current node">

- Select **Existing** from the dropdown under `Install State on` for **STATE** in the **Control plane** panel.
- Enter a password for the root GitLab user.
- Enter the IP address of your GitLab instance.  This should be an Ubuntu 14.04 machine with ports 80, 443, and 22 accessible to the other Shippable components and services.

You will need to click the **Apply** button after completing other sections. Installation progress (initializing or initialized) will be shown on the right side of the Control plane panel.

## Viewing configuration

Once GitLab is initializing, you'll be able to view the configuration and logs.

<img src="/images/platform/admiral/admiral-gitlab-config.png" alt="GitLab config">

## Viewing logs

The **Logs** button (paper clip icon) for **STATE** will show the logs from installation and initialization.

<img src="/images/platform/admiral/admiral-gitlab-logs.png" alt="GitLab logs">

# Chat Integration

This readme details how to integrate DataMiner into business communication platforms with Automation scripts.

## Table of Contents

- [Prerequisites](#prerequisites)
  - [Development](#Development)
    - [Skyline.DataMiner.DcpChatIntegrationHelper NuGet Package](#skyline.dataminer.dcpchatintegrationhelper-nuget-package)
    - [DataMiner Integration Studio Visual Studio Extension](#dataminer-integration-studio-visual-studio-extension)
  - [Usage](#Usage)
    - [General](#general)
    - [Microsoft Teams](#microsoft-teams)
- [Examples](#examples)
  - [General](#general-1)
  - [Microsoft Teams](#microsoft-teams-1) 
    * [Getting Started](#getting-started)
    * [Creating a Team](#creating-a-team)
    * [Creating a Channel](#creating-a-channel)
    * [Adding Team Members](#adding-team-members)
    * [Adding Team Owners](#adding-team-owners)
    * [Sending a Channel Notification](#sending-a-channel-notification)
- [Help](#help)
- [Contact](#contact)
- [Version History](#version-history)
- [License](#license)

## Prerequisites

### Development

#### Skyline.DataMiner.DcpChatIntegrationHelper NuGet Package

The Skyline.DataMiner.DcpChatIntegrationHelper NuGet package can be found on [nuget.org](https://nuget.org). This Nuget package allows easy integration with business communication platforms from a DataMiner Automation script.

> ℹ️
> We recommend that you always use the latest version of the Skyline.DataMiner.DcpChatIntegrationHelper NuGet package.

#### DataMiner Integration Studio Visual Studio Extension

The DataMiner Integration Studio Visual Studio extension (also referred to as DIS) is required for development of Automation scripts using the [Skyline.DataMiner.DcpChatIntegrationHelper NuGet package](#skyline.dataminer.dcpchatintegrationhelper-nuget-package). You can also use DIS to deploy Automation scripts directly from your development environment to your DataMiner Systems.

See [Installing DataMiner Integration Studio](https://aka.dataminer.services/DisInstallation).

> ℹ️
> We recommend that you always use the latest version of the DataMiner Integration Studio Visual Studio extension.

### Usage

#### General

- The DataMiner System must be cloud-connected. See [Connecting your DataMiner System to the cloud](https://docs.dataminer.services/user-guide/Cloud_Platform/AboutCloudPlatform/Connecting_your_DataMiner_System_to_the_cloud.html).

- The CloudGateway module must be updated to at least version 2.9.0. See [Upgrading nodes to the latest DxM versions](https://docs.dataminer.services/user-guide/Cloud_Platform/CloudAdminApp/Managing_cloud-connected_nodes.html).

#### Microsoft Teams

- The [DataMiner bot](https://teams.microsoft.com/l/app/9a09d087-5d07-4481-b34f-cd053eab7925) must be allowed in your [Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/manage-apps).

- Admin consent must be granted in the [DCP Admin app](https://docs.dataminer.services/user-guide/Cloud_Platform/CloudAdminApp/Granting_admin_consent.html).

## Examples

### General

- The code for these Automation scripts can be found in [the ChatIntegrationExamples folder](ChatIntegrationExamples).

### Microsoft Teams

#### Getting Started

1. [Download this DMAPP]() and [deploy it to your DataMiner System](https://docs.dataminer.services/develop/TOOLS/TOOApplicationPackages/Installing_an_app_package.html). Installing this package will add the Automation scripts for Microsoft Teams in the Automation module along with some memory files that will be used by the Automation scripts to save the IDs of the created resources.

   > Note that reinstalling this DMAPP will overwrite any Automation scripts and memory files with identical names.

2. [Open DataMiner Cube](https://docs.dataminer.services/user-guide/Getting_started/Accessing_DataMiner/Accessing_DataMiner_Cube.html) and open the Automation module (via apps > Automation). The added Automation scripts will be shown there. <details><summary>`show demo`</summary>![Gif-Automation](https://user-images.githubusercontent.com/109528797/186685478-9eac1cbf-f2d9-4c9a-8a6a-a2f499dbdcd9.gif)</details>

#### Creating a Team

1. In the Automation module in DataMiner Cube, click the '*Create Team*' Automation script and click the '*Execute*' button.

2. Fill in the necessary information. Note that the **fields are case sensitive**.

   - *Team Owner Email*: The email address of the owner of the team you are creating.
   - *Team Name*: The name of the team you are creating.
   - *Teams*: Select the memory file the script should use to save the ID of the team you are creating.

3. Click the '*execute now*' button.  A team (with a General channel) will be created in Microsoft Teams. The [DataMiner bot](https://teams.microsoft.com/l/app/9a09d087-5d07-4481-b34f-cd053eab7925) will also be installed. <details><summary>`show demo`</summary>![Gif-CreateTeam](https://user-images.githubusercontent.com/109528797/186685886-ae5f1834-1c5c-438d-92e7-03740330e51d.gif)</details>

#### Creating a Channel

1. First make sure [a team is created as detailed above](#creating-a-team), as a channel can only exist within a team.

2. In the Automation module in DataMiner Cube, click the '*Create Channel*' Automation script and click the '*Execute*' button.

3. Fill in the necessary information. Note that the **fields are case sensitive**.

   - *Team ID*: The ID of the team that should contain the channel.
   - *Channel Name*: The name of the channel you are creating.
   - *Channel Description*: The description of the channel you are creating.
   - *Channels*: Select the memory file the script should use to save the ID of the channel you are creating.

4. Click the '*execute now*' button. A channel will be created in Microsoft Teams. <details><summary>`show demo`</summary>![Gif-CreateChannel](https://user-images.githubusercontent.com/109528797/186855003-c4002e8e-c9cf-42fd-91bd-b389d4bab908.gif)</details>

#### Adding Team Members

To add a new member or members to a team:

1. First make sure [a team is created as detailed above](#creating-a-team), as members can only exist within a team.

2. In the Automation module in DataMiner Cube, click the '*Add Team Members*' Automation script and click the '*Execute*' button.

3. Fill in the necessary information. Note that the **fields are case sensitive**.

   - *Team ID*: The ID of the team where you want to add one or more new members.
   - *Team Members to Add*: The email addresses of the members, separated by semicolons (";").

4. Click the '*execute now*' button. The members will be added to the team in Microsoft Teams. <details><summary>`show demo`</summary>![Gif-AddTeamMember](https://user-images.githubusercontent.com/109528797/186880110-4fb9a616-b647-4919-9556-4a057a65be2b.gif)</details>

#### Adding Team Owners

To add a new owner or owners to a team:

1. First make sure [a team is created as detailed above](#creating-a-team), as owners can only exist within a team.

2. In the Automation module in DataMiner Cube, click the '*Add Team Owners*' Automation script and click the '*Execute*' button.

3. Fill in the necessary information. Note that the **fields are case sensitive**.

   - *Team ID*: The ID of the team where you want to add one or more new owners.
   - *Team Owners to Add*: The email addresses of the new owners, separated by semicolons (";").

4. Click the '*execute now*' button. An owner will be added to the team in Microsoft Teams. <details><summary>`show demo`</summary>![Gif-AddTeamOwner](https://user-images.githubusercontent.com/109528797/187139084-f2991b40-cbe2-46fe-aec9-c804b9852e62.gif)</details>

#### Sending a Channel Notification

To send a notification in a channel:

1. First make sure [a channel is created as detailed above](#creating-a-channel), as notifications can only be posted within a channel.

2. In the Automation module in DataMiner Cube, click the '*Send Channel Notification*' Automation script and click the '*Execute*' button.

3. Fill in the necessary information. Note that the **fields are case sensitive**.

   - *Team ID*: The ID of the team where you want to send a notification.
   - *Channel ID*: The ID of the channel where you want to send a notification. Note that this must be a channel of the specified team.
   - *Notification*: The text of the notification.

4. Click the '*execute now*' button. A notification will be sent in Microsoft Teams. <details><summary>`show demo`</summary>![Gif-SendNotification](https://user-images.githubusercontent.com/109528797/187139103-4728e148-204d-447f-9674-8d74f4e373d1.gif)</details>

## Help

[Skyline Communications: Support](https://skyline.be/contact/tech-support)

## Contact

[Skyline Communications: Contact](https://skyline.be/contact)

## Version History

[Releases](https://github.com/SkylineCommunications/chat-integration/releases)

## License

This project is licensed under the [MIT License](https://github.com/SkylineCommunications/chat-integration/blob/main/LICENSE) – see the file for details.

# JCB! Fields

### What Are Fields?
Fields are the **foundation** of every Joomla Component Builder (JCB) project.

They define how data is **stored**, **validated**, **rendered**, and **interacted with** in your Joomla extensions.

Fields let you control everything from the **underlying database schema** to the **user interface**, all within a single configuration.

Each Field:
- Defines **database structure** (type, size, default, null, unique keys, indexes)
- Binds to a **fieldtype**, determining HTML rendering and behavior
- Supports per-field **custom PHP** for model saving and retrieval
- Allows styling and scripting (HTML attributes, JS, CSS)
- Automatically generates Joomla-compliant XML field definitions

### Where Are Fields Used in JCB?
Fields are universal integrated — they are used in, highly structured areas:

- ✅ **Admin Views** (the native Joomla back-end editing views)
- ✅ **Modules** (frontend display configurations)
- ✅ **Plugins** (event-driven integrations)
- ✅ **Component Configurations** (global parameter settings)

### What Can a Field Do?
A Field in JCB can define:

- **Database Type & Schema**: `int`, `varchar`, `json`, custom, nullable, defaults, indexes
- **Permissions**: who can view/edit the field (ACL)
- **Rendering Options**: HTML classes, labels, JS behaviors
- **Model Integration**: how the value is saved or retrieved
- **Dynamic Logic**: PHP hooks for `onGet`, `onSave`, `onPrepareForm`, etc.
- **Fieldtypes**: link to rich behaviors like Model Selects, Subforms, Toggle Switches, Encrypted Fields, etc.

This centralization makes field management efficient and highly reusable.

### Reuse and Sharing
Fields are standalone entities:

- Define once, **reuse across multiple Admin Views**, Modules, or Plugins
- Fields can also be exported and shared via repositories
- JCB will automatically adjust them to fit into each consuming context

This means less duplication, and greater consistency across your entire component structure.

### Versioning and Customization
To update a field:

- Click **"reset"** in the JCB UI to sync with this repository
- Or **fork** this repository, customize the field, and point JCB to your fork

This preserves version control while allowing your own field improvements to live independently.

>Fields define both structure and behavior — they are where your data comes alive.

---
### Index of Fields


 - **1 stop** | [Details](src/field/934eb37b-0fb1-4fed-b3ec-969cd0b364ee) | [Settings](src/field/934eb37b-0fb1-4fed-b3ec-969cd0b364ee/item.json)
 - **2 stop** | [Details](src/field/4a87c014-04ca-4986-8aea-43ed407ff07a) | [Settings](src/field/4a87c014-04ca-4986-8aea-43ed407ff07a/item.json)
 - **3 stop** | [Details](src/field/f68fdba1-62f1-4396-b915-cacc79206db5) | [Settings](src/field/f68fdba1-62f1-4396-b915-cacc79206db5/item.json)
 - **Altitude** | [Details](src/field/bdee9804-cf65-46da-a49a-5397789c801e) | [Settings](src/field/bdee9804-cf65-46da-a49a-5397789c801e/item.json)
 - **Availability** | [Details](src/field/7d158094-5df6-4486-87d9-d1c3f6732ced) | [Settings](src/field/7d158094-5df6-4486-87d9-d1c3f6732ced/item.json)
 - **Base** | [Details](src/field/cf7146a0-8c47-4fec-9490-34287ef14408) | [Settings](src/field/cf7146a0-8c47-4fec-9490-34287ef14408/item.json)
 - **Camp fire** | [Details](src/field/e984295c-77bf-437b-8361-4977646fae4c) | [Settings](src/field/e984295c-77bf-437b-8361-4977646fae4c/item.json)
 - **Camp fire comments** | [Details](src/field/790e3092-af3f-4179-859f-8362a33bff8d) | [Settings](src/field/790e3092-af3f-4179-859f-8362a33bff8d/item.json)
 - **Credits** | [Details](src/field/897b1866-93ae-4c77-9d76-2d59fe32fc83) | [Settings](src/field/897b1866-93ae-4c77-9d76-2d59fe32fc83/item.json)
 - **Date (required)** | [Details](src/field/03995043-13fb-4ec7-bc66-e13434425a06) | [Settings](src/field/03995043-13fb-4ec7-bc66-e13434425a06/item.json)
 - **Electricity** | [Details](src/field/85beced9-a24c-4797-a94b-5aa7c460076e) | [Settings](src/field/85beced9-a24c-4797-a94b-5aa7c460076e/item.json)
 - **Electricity_comments** | [Details](src/field/e302de6a-6249-4ced-9894-ee0cf9a79e28) | [Settings](src/field/e302de6a-6249-4ced-9894-ee0cf9a79e28/item.json)
 - **Group** | [Details](src/field/0d4a5caa-2199-4fb1-b07f-bd8071d71dbe) | [Settings](src/field/0d4a5caa-2199-4fb1-b07f-bd8071d71dbe/item.json)
 - **Heating** | [Details](src/field/fd05b628-8b23-42fc-aacc-78ebcf96ea60) | [Settings](src/field/fd05b628-8b23-42fc-aacc-78ebcf96ea60/item.json)
 - **Heating_comments** | [Details](src/field/cf695cba-a05d-422d-9886-d964feaad393) | [Settings](src/field/cf695cba-a05d-422d-9886-d964feaad393/item.json)
 - **Identification code** | [Details](src/field/68699537-3391-400c-af78-177327570b4e) | [Settings](src/field/68699537-3391-400c-af78-177327570b4e/item.json)
 - **Image** | [Details](src/field/3df662f4-5924-483e-8636-24c2ed4f27bf) | [Settings](src/field/3df662f4-5924-483e-8636-24c2ed4f27bf/item.json)
 - **Kitchen** | [Details](src/field/7b541f51-6f3f-4f78-a8b4-2dd3009714d7) | [Settings](src/field/7b541f51-6f3f-4f78-a8b4-2dd3009714d7/item.json)
 - **Kitchen_comments** | [Details](src/field/f8c6ddf1-eee0-408d-9634-b7ff3b19193f) | [Settings](src/field/f8c6ddf1-eee0-408d-9634-b7ff3b19193f/item.json)
 - **Latitude (decimal)** | [Details](src/field/b83771c3-ffd1-4827-a41d-a633873517c7) | [Settings](src/field/b83771c3-ffd1-4827-a41d-a633873517c7/item.json)
 - **Location** | [Details](src/field/44ac0436-5edb-4787-acea-afc18da84380) | [Settings](src/field/44ac0436-5edb-4787-acea-afc18da84380/item.json)
 - **Long description** | [Details](src/field/382f24f4-aea2-448e-927c-99d89bb6ed40) | [Settings](src/field/382f24f4-aea2-448e-927c-99d89bb6ed40/item.json)
 - **Longitude (decimal)** | [Details](src/field/2c6061d1-eb07-4f29-858b-21e4439b237b) | [Settings](src/field/2c6061d1-eb07-4f29-858b-21e4439b237b/item.json)
 - **Name** | [Details](src/field/ea8871b6-4f71-480b-bbd7-0d71322c6464) | [Settings](src/field/ea8871b6-4f71-480b-bbd7-0d71322c6464/item.json)
 - **Place** | [Details](src/field/7650ce92-9234-4805-a2b0-a083eb910a2d) | [Settings](src/field/7650ce92-9234-4805-a2b0-a083eb910a2d/item.json)
 - **Place_id** | [Details](src/field/143b101b-a9c9-41eb-9f23-ebf9e9b1146b) | [Settings](src/field/143b101b-a9c9-41eb-9f23-ebf9e9b1146b/item.json)
 - **Places inside** | [Details](src/field/00ea1e01-ff68-4feb-8649-68c63d4e062c) | [Settings](src/field/00ea1e01-ff68-4feb-8649-68c63d4e062c/item.json)
 - **Places outside** | [Details](src/field/aaf3f211-ba95-45cc-a2a1-881d6ea35d50) | [Settings](src/field/aaf3f211-ba95-45cc-a2a1-881d6ea35d50/item.json)
 - **Rest rooms** | [Details](src/field/d3a5af2d-6b37-49ba-a4b6-0940501091f8) | [Settings](src/field/d3a5af2d-6b37-49ba-a4b6-0940501091f8/item.json)
 - **Rest rooms checkbox** | [Details](src/field/7b8c2df6-7725-4d31-ac4f-adf9d4e3b5a7) | [Settings](src/field/7b8c2df6-7725-4d31-ac4f-adf9d4e3b5a7/item.json)
 - **Rest rooms comments** | [Details](src/field/cca6eefd-e461-430b-9213-62255017eb5d) | [Settings](src/field/cca6eefd-e461-430b-9213-62255017eb5d/item.json)
 - **Security rules** | [Details](src/field/e5acc3ed-593b-4318-a3fd-47a82e47bf45) | [Settings](src/field/e5acc3ed-593b-4318-a3fd-47a82e47bf45/item.json)
 - **Short Description** | [Details](src/field/c9896d41-82cf-42da-873f-2b7c59e22b81) | [Settings](src/field/c9896d41-82cf-42da-873f-2b7c59e22b81/item.json)
 - **Stop** | [Details](src/field/2d01d455-4120-45bf-bce3-eba4354989c0) | [Settings](src/field/2d01d455-4120-45bf-bce3-eba4354989c0/item.json)
 - **Telephone** | [Details](src/field/096fd1f5-480a-4a8b-98cf-4fceac5e7999) | [Settings](src/field/096fd1f5-480a-4a8b-98cf-4fceac5e7999/item.json)
 - **Trek** | [Details](src/field/ad024e94-3ce7-41cb-80c3-9b44bc9387d5) | [Settings](src/field/ad024e94-3ce7-41cb-80c3-9b44bc9387d5/item.json)
 - **Water comments** | [Details](src/field/7b9ada22-e39d-4ed6-8486-a0d81f31a709) | [Settings](src/field/7b9ada22-e39d-4ed6-8486-a0d81f31a709/item.json)
 - **ta** | [Details](src/field/96d63e51-c004-42f0-8dd4-ffd711ad391e) | [Settings](src/field/96d63e51-c004-42f0-8dd4-ffd711ad391e/item.json)
 - **tb** | [Details](src/field/64dc5d42-2334-46e7-8372-e1b5e2ac9424) | [Settings](src/field/64dc5d42-2334-46e7-8372-e1b5e2ac9424/item.json)

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
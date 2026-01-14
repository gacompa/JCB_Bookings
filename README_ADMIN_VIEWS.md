# JCB! Admin Views

### What Are Admin Views?
**Admin Views** form the foundational interface layer of every JCB-built Joomla component.

Each Admin View is tightly bound to a database table and automatically generates all required:
- **Forms**
- **Models**
- **Controllers**
- **List and Edit Views**
- **Permission handling** (ACL)
- **Field validation and access control**

Admin Views are mandatory. Every JCB component must include at least one Admin View  
to be valid and compile correctly. This ensures that your component manages data  
within Joomla's native MVC architecture — offering full CRUD capabilities out-of-the-box.

---
### Why Are Admin Views Important?
Admin Views serve as the **data anchor** for the component:

- Link directly to Joomla database tables
- Automatically attach multiple fields and manage field visibility/edit permissions
- Enable subforms (linking to other Admin Views) for nested data structures
- Respect Joomla's ACL per view and field
- Reusable across multiple components — compile-safe with namespace awareness

This makes Admin Views the heart of every component, defining its schema, edit experience,  
and administrative backbone. Unlike Custom Admin Views or Site Views (which focus more on layout or data rendering),  
Admin Views define the **structural data definition** and baseline logic.

---
### Versioning and Sharing
When you need to update Admin Views in any JCB project:

- Select the views to update
- Click **"Reset"** to pull the latest version from this repository
- Or **Fork** this repository and point your JCB instance to your fork

This ensures maintainability while still allowing total customization per project.

>Admin Views are the schema-defining force in JCB — not just a UI pattern, but a declaration of how your component should structure and manage its data. We recommend exploring the shipped demo component to see Admin Views in action.

---
### Index of Admin Views


 - **DJ Main Topics** | [Details](src/admin_view/e3b0b470-2798-472f-bfba-e5b6b84c16ea) | [Settings](src/admin_view/e3b0b470-2798-472f-bfba-e5b6b84c16ea/item.json) | The project describbed in notes
 - **DJ Projects** | [Details](src/admin_view/6db8fea1-72a7-41a8-bcfe-ef6073b3785f) | [Settings](src/admin_view/6db8fea1-72a7-41a8-bcfe-ef6073b3785f/item.json) | The project describbed in notes
 - **DJ Topics** | [Details](src/admin_view/01965bed-98ca-40e5-a14c-9f0e3dad095b) | [Settings](src/admin_view/01965bed-98ca-40e5-a14c-9f0e3dad095b/item.json) | The project describbed in notes
 - **DJ report rows** | [Details](src/admin_view/3e11ed08-d4ec-4aba-9f6b-7df772a2a997) | [Settings](src/admin_view/3e11ed08-d4ec-4aba-9f6b-7df772a2a997/item.json) | Rows for development notes
 - **DJ rows** | [Details](src/admin_view/b646e37c-9675-4fe3-8937-2942a734dd20) | [Settings](src/admin_view/b646e37c-9675-4fe3-8937-2942a734dd20/item.json) | Rows for development notes
 - **Destinazione** | [Details](src/admin_view/ab6a58ce-5d20-4c0a-819b-78b06c1f6535) | [Settings](src/admin_view/ab6a58ce-5d20-4c0a-819b-78b06c1f6535/item.json) | Destinazioni
 - **Locations** | [Details](src/admin_view/eafd26f7-b13c-4c36-b8a3-ae7d71febb24) | [Settings](src/admin_view/eafd26f7-b13c-4c36-b8a3-ae7d71febb24/item.json) | List of the locations in the area
 - **Paths** | [Details](src/admin_view/858b0999-8350-46a5-9c4e-e0e715aa8b1a) | [Settings](src/admin_view/858b0999-8350-46a5-9c4e-e0e715aa8b1a/item.json) | Paths
 - **Places** | [Details](src/admin_view/55aac7da-e105-4ab2-9c34-6ee44e8b692c) | [Settings](src/admin_view/55aac7da-e105-4ab2-9c34-6ee44e8b692c/item.json) | Relevant places in the area
 - **Reservations** | [Details](src/admin_view/e42d4c2d-ccd3-4291-a886-6f958be29417) | [Settings](src/admin_view/e42d4c2d-ccd3-4291-a886-6f958be29417/item.json) | Reservation
 - **Reservations-edit** | [Details](src/admin_view/1f70dec6-20b6-4ef7-b4aa-e50b86cf98f3) | [Settings](src/admin_view/1f70dec6-20b6-4ef7-b4aa-e50b86cf98f3/item.json) | Reservation
 - **Tickets** | [Details](src/admin_view/f9a01525-1db5-47ee-8ba7-8ce44a10bb99) | [Settings](src/admin_view/f9a01525-1db5-47ee-8ba7-8ce44a10bb99/item.json) | Tickets on the component
 - **Treks** | [Details](src/admin_view/5274216a-5a18-4e25-81e6-f006d1344781) | [Settings](src/admin_view/5274216a-5a18-4e25-81e6-f006d1344781/item.json) | Treks
 - **tas** | [Details](src/admin_view/f178a13e-e364-4d49-b39c-b77bac931787) | [Settings](src/admin_view/f178a13e-e364-4d49-b39c-b77bac931787/item.json) | ta
 - **tbs** | [Details](src/admin_view/33c892eb-470a-4424-bdb9-08c4e9c0c7b2) | [Settings](src/admin_view/33c892eb-470a-4424-bdb9-08c4e9c0c7b2/item.json) | tb
 - **tcs** | [Details](src/admin_view/d33d1bae-79cc-4c3c-9a22-5fe7e493f014) | [Settings](src/admin_view/d33d1bae-79cc-4c3c-9a22-5fe7e493f014/item.json) | tc
 - **tds** | [Details](src/admin_view/d0ca72ca-014b-48ce-8828-96311ad04c1b) | [Settings](src/admin_view/d0ca72ca-014b-48ce-8828-96311ad04c1b/item.json) | td
 - **test** | [Details](src/admin_view/6bf8c6a1-36f3-4c13-b04d-89eefe322d0f) | [Settings](src/admin_view/6bf8c6a1-36f3-4c13-b04d-89eefe322d0f/item.json) | test

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
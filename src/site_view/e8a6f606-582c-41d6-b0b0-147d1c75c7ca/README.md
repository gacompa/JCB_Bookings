### JCB! Site View
# Path single (path_single)

Display on one path

## HTML:
```html
<?php 
// Get the application object.
$app = JFactory::getApplication();
// Get the JInput object.
$jinput = $app->input;
//Using getInt() ensures that the value is treated as a secure integer, which is crucial for preventing SQL injection and other vulnerabilities.
$itemId = $jinput->getInt('id');
?>

<?php
{
    // Get a database connection.
    $db = JFactory::getDbo();

    // Create a new query object.
    $query = $db->getQuery(true);

    // Build the query to select all columns for the item with the given ID.
    $query->select('*')
          ->from('#__bookings_path')
          ->where('id = ' . (int) $itemId);

    // Set the query and load the result as a single object.
    $db->setQuery($query);
    $item = $db->loadObject();
}
?>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout Dettagli Completo</title>
    <style>
        /* Base Reset and Body Styling */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        /* --- 1. TITLE ROW --- */
        .title-row {
             background-color: #4CAF50; /* Verde for header*/
            color: white;
            padding: 15px 20px;
            font-size: 1.8em;
            text-align: center;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        /* --- 2. MAIN CONTENT CONTAINER (Image + Map) --- */
        .main-content-container {
            display: flex; /* Enables Flexbox for side-by-side layout */
            flex-wrap: wrap; /* Allows wrapping on smaller screens */
            padding: 20px;
            gap: 20px; /* Space between the image and map columns */
        }

        /* --- 3. DETAIL TABLE ROW --- */
        .detail-table-row {
            padding: 0 20px 20px;
        }

        .data-table {
            width: 100%;
            border-collapse: collapse;
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }

        .data-table th, .data-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        .data-table th {
            background-color: #f2f2f2;
            font-weight: bold;
            color: #333;
        }

        .data-table tr:last-child td {
            border-bottom: none;
        }

        /* --- RESPONSIVENESS (Mobile View) --- */
        @media (max-width: 800px) {
            .main-content-container {
                flex-direction: column; /* Stack columns vertically on small screens */
            }

            .image-column, .map-column {
                flex: 1 1 100%; /* Each item takes 100% width */
                max-width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="title-row">
        <?php echo $item->path ; ?>
    </div>

    <div class="detail-table-row">
    <table>
	    <tr>
	    	<td style="width:60% ; vertical-align:top"> <?php echo $item->longdescription; ?> </td>
	    	<td style="width:40% ; vertical-align:top"> <?php echo "<p><iframe $item->komoot_embed_code </iframe></p>"; ?> </td>
	    </tr>
	</table>
    </div>

</body>
</form>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
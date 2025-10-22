### JCB! Site View
# Locations (locations)

Site locations

## HTML:
```html
<form action="<?php echo Route::_('index.php?option=com_bookings'); ?>" method="post" name="adminForm" id="adminForm">
<?php echo $this->toolbar->render(); ?>
<?php echo LayoutHelper::render('rowslocations', []); ?>

<!-- Put here the route for the one-location view, i.e. index.php/booking/one-location -->
<?php $one_location_path = "index.php/booking/one-location"; ?>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Box con Tre Sezioni</title>
    <style>
        /* Stili per il contenitore principale */
        .custom-box {
            width: 650px; /* Larghezza del box aumentata leggermente */
            border: 1px solid #ccc;
            border-radius: 12px; /* Angoli arrotondati */
            overflow: hidden; 
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            font-family: Arial, sans-serif;
            margin: 20px; /* Margine per visualizzazione */
        }

        /* --- PRIMA RIGA: BARRA SUPERIORE VERDE --- */
        .top-bar {
            background-color: #4CAF50; /* Verde */
            color: white;
            padding: 10px 15px;
            font-size: 1.2em;
            font-weight: bold;
        }

        /* --- SECONDA RIGA: CONTENUTO PRINCIPALE (IMMAGINE + TESTO) --- */
        .middle-content {
            padding: 15px;
            display: flow-root; /* Alternativa a clearfix per contenere i float */
            border-bottom: 1px solid #eee; /* Separatore visivo */
        }

        .image-container {
            float: left; /* Posiziona a sinistra */
            width: 30%; 
            margin-right: 20px; 
        }

        .image-container img {
            width: 100%; 
            height: auto;
            display: block;
            border-radius: 8px; 
        }


        /* The Modal/Lightbox (hidden by default) */
        .lightbox {
            display: none; /* Hidden by default */
            position: fixed; /* Stay fixed on the screen */
           z-index: 9999; /* Sit on top of everything */
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto; /* Enable scroll if needed */
            background-color: rgba(0, 0, 0, 0.9); /* Black background with opacity */
        }

        /* Image inside the Modal */
        .lightbox-content {
            margin: auto;
            display: block;
            max-width: 90%; /* Limits the image width */
            max-height: 90vh; /* Limits the image height to 90% of the viewport height */
            position: relative;
            top: 50%;
            transform: translateY(-50%); /* Centers vertically */
        }

        /* The Close Button */
        .close-button {
            position: absolute;
            top: 15px;
            right: 35px;
            color: #f1f1f1;
            font-size: 40px;
            font-weight: bold;
            transition: 0.3s;
            cursor: pointer;
        }

        .text-content {
            overflow: hidden; /* Occupa lo spazio rimanente a destra */
        }

        .text-content h3 {
            margin-top: 0;
            color: #333;
        }

        /* --- TERZA RIGA: TABELLA DATI --- */
        .bottom-content {
            padding: 15px;
        }
        
        .data-table {
            width: 100%;
            border-collapse: collapse; /* Rimuove lo spazio tra le celle */
        }

        .data-table td {
            padding: 8px 15px;
            border-bottom: 1px solid #f0f0f0;
            font-size: 0.9em;
        }

        .data-table tr:last-child td {
            border-bottom: none; /* Rimuove il bordo dall'ultima riga */
        }

        .data-table .label {
            width: 40%;
            font-weight: bold;
            color: #555;
            background-color: #f9f9f9;
        }

        .data-table .value {
            width: 60%;
            color: #333;
        }

    </style>
</head>

<?php foreach ($this->items as $item): ?>
<body>

<div class="custom-box">
    <div class="top-bar">
<b><?php echo "<a href=\"$one_location_path?id=$item->id\" > $item->name </a>"; ?></b><br/><?php echo $item->description; ?>    </div>
    
<div class="middle-content">

    <div class="image-container">
        <?php $baseurl = Uri::root(); ?>
        <?php $fullImageUrl = $baseurl . $item->image; ?>
        <img 
            src="<?php echo $item->image; ?>" 
            alt="Click to Enlarge" 
            onclick="openLightbox('<?php echo htmlspecialchars($fullImageUrl); ?>')"
            style="cursor: pointer; width: 300px; height: auto;" 
        />
        <?php echo "Click image to enlarge" ; ?>
    </div>
    <div id="lightbox-modal" class="lightbox" onclick="closeLightbox()">
        <span class="close-button">&times;</span>
        <img id="lightbox-image" class="lightbox-content" src="<?php echo JPATH_ROOT . "/" .  $item->image; ?>" alt="Enlarged Image">
    </div>       
    <div class="text-content">
        <p>
        <?php echo $item->longdescription ; ?>  
        </p>
    </div>
</div>

<div class="bottom-content">
        <table class="data-table">
            <tr>
                <td class="label"><?php echo JText::_('Altitude'); ?> </td>
                <td class="value"><?php echo $item->place_altitude ; ?> </td>
            </tr>
            <tr>
                <td class="label"><?php echo JText::_('Type'); ?> </td>
                <td class="value"><?php echo ($item->is_base) ? JText::_('Is a base' ) : JText::_('Is NOT a base' ); echo " | "; echo ($item->is_stop) ? JText::_('Is a stop' ) : JText::_('Is NOT a stop' ); ?> </td>
            </tr>
          <?php if ($item->is_stop) { ?>
            <tr>
                <td class="label"><?php echo JText::_('Places indoor | outdoor'); ?> </td>
                <td class="value"><?php echo $item->places_indoor . " indoor | " . $item->places_outdoor . " outdoor"; ?> </td>
            </tr>
            <?php } ?>
            <tr>
                <td class="label">Posti Letto</td>
                <td class="value">35</td>
            </tr>
        </table>
    </div>
</div>
</body>
<?php endforeach; ?>

<?php if (isset($this->items) && isset($this->pagination) && isset($this->pagination->pagesTotal) && $this->pagination->pagesTotal > 1): ?>
	<div class="pagination">
		<?php if ($this->params->def('show_pagination_results', 1)) : ?>
			<p class="counter pull-right"> <?php echo $this->pagination->getPagesCounter(); ?> <?php echo $this->pagination->getLimitBox(); ?></p>
		<?php endif; ?>
		<?php echo $this->pagination->getPagesLinks(); ?>
	</div>
<?php endif; ?>
<input type="hidden" name="task" value="" />
<?php echo Html::_('form.token'); ?>
</form>

<script>
function openLightbox(imageSource) {
    // Get the modal and image elements
    const modal = document.getElementById('lightbox-modal');
    const modalImg = document.getElementById('lightbox-image');

    // Set the image source and display the modal
    modalImg.src = imageSource;
    modal.style.display = 'block';
}

function closeLightbox() {
    const modal = document.getElementById('lightbox-modal');
    modal.style.display = 'none';
}

// Optional: Close the modal if the user presses the ESC key
document.addEventListener('keydown', function(event) {
    if (event.key === "Escape") {
        closeLightbox();
    }
});
</script>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
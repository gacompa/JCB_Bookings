### JCB! Site View
# Places (places)

places

## HTML:
```html
<div class="container-fluid">
    <div class="table-responsive">
        <table class="table table-hover table-striped">
            <thead class="bg-gray-100">
                <tr>
                    <th class="py-2 px-4 text-left font-semibold">Select</th>
                    <th class="py-2 px-4 text-left font-semibold">Place Name</th>
                </tr>
            </thead>
            <tbody>
                <?php if (!empty($this->items)): ?>
                    <?php foreach ($this->items as $item): ?>
                        <tr>
                            <td class="py-2 px-4">
                                <input type="radio" name="selected_location" value="<?php echo (int) $item->id; ?>" data-place="<?php echo $this->escape($item->place); ?>">
                            </td>
                            <td class="py-2 px-4"><?php echo $this->escape($item->place); ?></td>
                        </tr>
                    <?php endforeach; ?>
                <?php else: ?>
                    <tr>
                        <td colspan="2" class="text-center py-4">No locations found.</td>
                    </tr>
                <?php endif; ?>
            </tbody>
        </table>
    </div>

    <!-- A "Done" button to submit the selections -->
    <div class="mt-4 text-center">
        <button
            type="button"
            class="btn bg-green-500 hover:bg-green-600 text-white font-bold py-2 px-4 rounded-lg shadow-sm transition-colors"
            onclick="Joomla.selectLocations();"
        >
            Done
        </button>
    </div>
</div>

<script>
    // Ensure the Joomla object exists
    if (typeof Joomla === 'undefined') {
        var Joomla = {};
    }

    /**
     * This function is called when a user selects a location from the modal.
     * It populates the parent window's form fields and closes the modal.
     */
    Joomla.selectLocations = function () {
        // Find the single checked radio button
        const selectedRadio = document.querySelector('input[name="selected_location"]:checked');

        if (selectedRadio) {
            // Get the ID and place name from the selected radio button
            const selectedId = selectedRadio.value;
            const selectedPlace = selectedRadio.dataset.place;
            
            // Access the parent window and update the input fields.
            window.parent.document.getElementById('location_id').value = selectedId;
            window.parent.document.getElementById('location_title').value = selectedPlace;
        } else {
            // Clear the parent fields if no item is selected
            window.parent.document.getElementById('location_id').value = '';
            window.parent.document.getElementById('location_title').value = '';
        }

        // Close the modal.
        // We use jQuery here as Bootstrap's modal() method is often more reliable.
        window.parent.jQuery('#locationModal').modal('hide');
    };
</script>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
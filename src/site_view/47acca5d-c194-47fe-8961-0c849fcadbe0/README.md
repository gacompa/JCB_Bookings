### JCB! Site View
# Location (onelocation)

One site location

## HTML:
```html
<?php echo $this->toolbar->render(); ?>

<?php echo $this->toolbar->render(); ?>
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
          ->from('#__bookings_location')
          ->where('id = ' . (int) $itemId);

    // Set the query and load the result as a single object.
    $db->setQuery($query);
    $item = $db->loadObject();

}
?>
<table class="uk-table uk-table-hover">
    <caption><?php echo Text::_('LOCATIONS'); ?></caption>
    <tbody>
        <tr> <td><img src="<?php echo $item->image; ?>" style="width: 75%; height: auto"> </td> </tr>
        <tr> <td><b><?php echo $item->name ; ?></b><?php echo " - ".$item->description; ?></td> </tr>
        <tr> <td><?php echo $item->altitude." m s.l.m."; ?></td> </tr>
        <tr> <td>
          <!-- tent icon by Free Icons (https://free-icons.github.io/free-icons/) -->
          <svg xmlns="http://www.w3.org/2000/svg" height="1em" fill="currentColor" viewBox="0 0 512 512">
          <path d="M 239.16955017301038 37.20415224913495 Q 256 26.57439446366782 272.8304498269896 37.20415224913495 L 471.25259515570934 178.93425605536333 L 471.25259515570934 178.93425605536333 Q 480.9965397923875 186.02076124567475 482.7681660899654 199.30795847750866 L 511.11418685121106 454.42214532871975 L 511.11418685121106 454.42214532871975 Q 512 466.8235294117647 504.02768166089965 475.681660899654 Q 495.1695501730104 485.42560553633217 482.7681660899654 485.42560553633217 L 411.9031141868512 485.42560553633217 L 387.10034602076126 485.42560553633217 Q 369.3840830449827 484.53979238754323 361.4117647058824 469.48096885813146 L 272.8304498269896 292.318339100346 L 272.8304498269896 292.318339100346 Q 270.1730103806228 287.0034602076125 264.8581314878893 287.0034602076125 Q 256.88581314878894 287.88927335640136 256 295.8615916955017 L 256 457.0795847750865 L 256 457.0795847750865 Q 256 469.48096885813146 248.02768166089965 477.4532871972318 Q 240.05536332179932 485.42560553633217 227.65397923875432 485.42560553633217 L 213.4809688581315 485.42560553633217 L 29.231833910034602 485.42560553633217 Q 16.830449826989618 485.42560553633217 7.972318339100346 475.681660899654 Q 0 466.8235294117647 0.8858131487889274 453.5363321799308 L 29.231833910034602 198.42214532871972 L 29.231833910034602 198.42214532871972 Q 31.003460207612456 186.02076124567475 40.74740484429066 178.93425605536333 L 239.16955017301038 37.20415224913495 L 239.16955017301038 37.20415224913495 Z" />
          </svg>
          <?php $message= $item->is_stop ? "É" : "Non è"; ?>
          <?php echo "  " . $message . " una tappa di pernottamento" ?>
          <!-- house-flag icon by Free Icons (https://free-icons.github.io/free-icons/) -->
          <svg xmlns="http://www.w3.org/2000/svg" height="1em" fill="currentColor" viewBox="0 0 512 512">
          <path d="M 384.9922480620155 52.78759689922481 Q 373.8790697674419 52.78759689922481 366.7348837209302 59.93178294573644 L 366.7348837209302 59.93178294573644 L 366.7348837209302 59.93178294573644 Q 359.5906976744186 67.07596899224806 359.5906976744186 78.18914728682171 L 359.5906976744186 205.1968992248062 L 359.5906976744186 205.1968992248062 L 359.5906976744186 459.2124031007752 L 359.5906976744186 459.2124031007752 L 410.3937984496124 459.2124031007752 L 410.3937984496124 459.2124031007752 L 410.3937984496124 205.1968992248062 L 410.3937984496124 205.1968992248062 L 499.29922480620155 205.1968992248062 L 499.29922480620155 205.1968992248062 Q 511.2062015503876 204.4031007751938 512 192.49612403100775 L 512 90.88992248062016 L 512 90.88992248062016 Q 511.2062015503876 78.9829457364341 499.29922480620155 78.18914728682171 L 410.3937984496124 78.18914728682171 L 410.3937984496124 78.18914728682171 Q 410.3937984496124 67.07596899224806 403.2496124031008 59.93178294573644 Q 396.10542635658913 52.78759689922481 384.9922480620155 52.78759689922481 L 384.9922480620155 52.78759689922481 Z M 334.1891472868217 179.0015503875969 L 223.85116279069769 84.53953488372093 L 334.1891472868217 179.0015503875969 L 223.85116279069769 84.53953488372093 Q 207.1813953488372 71.83875968992248 190.51162790697674 84.53953488372093 L 12.70077519379845 236.94883720930233 L 12.70077519379845 236.94883720930233 Q 0 248.06201550387595 5.556589147286822 264.7317829457364 Q 11.906976744186046 280.6077519379845 29.370542635658914 281.4015503875969 L 54.77209302325581 281.4015503875969 L 54.77209302325581 281.4015503875969 L 54.77209302325581 433.8108527131783 L 54.77209302325581 433.8108527131783 Q 54.77209302325581 444.9240310077519 61.91627906976744 452.0682170542636 Q 69.06046511627908 459.2124031007752 80.17364341085272 459.2124031007752 L 130.97674418604652 459.2124031007752 L 130.97674418604652 459.2124031007752 Q 142.08992248062015 459.2124031007752 149.23410852713178 452.0682170542636 Q 156.37829457364342 444.9240310077519 156.37829457364342 433.8108527131783 L 156.37829457364342 357.6062015503876 L 156.37829457364342 357.6062015503876 Q 156.37829457364342 346.49302325581397 163.52248062015505 339.3488372093023 Q 170.66666666666666 332.2046511627907 181.77984496124031 332.2046511627907 L 232.5829457364341 332.2046511627907 L 232.5829457364341 332.2046511627907 Q 243.69612403100774 332.2046511627907 250.84031007751938 339.3488372093023 Q 257.984496124031 346.49302325581397 257.984496124031 357.6062015503876 L 257.984496124031 433.8108527131783 L 257.984496124031 433.8108527131783 Q 257.984496124031 444.9240310077519 265.1286821705426 452.0682170542636 Q 272.2728682170543 459.2124031007752 283.3860465116279 459.2124031007752 L 334.9829457364341 459.2124031007752 L 334.9829457364341 459.2124031007752 L 334.9829457364341 459.2124031007752 L 334.9829457364341 459.2124031007752 L 334.1891472868217 459.2124031007752 L 334.1891472868217 459.2124031007752 L 334.1891472868217 179.0015503875969 L 334.1891472868217 179.0015503875969 Z" />
          </svg>
          <?php $message= $item->is_base ? "É" : "Non è"; ?>
          <?php echo "  " . $message . " una base scout" ?>
        </td></tr>
    </tbody>


    <tbody>
      <tr> <td><?php echo $item->heating_checkbox  ; echo $item->heating_comments ;?> </td></tr>
      <tr> <td><?php echo $item->kitchen_checkbox  ; echo $item->kitchen_comments ;?> </td></tr>
      <tr> <td><?php echo $item->electricity_checkbox  ; echo $item->electricity_comments ;?> </td></tr>
      <tr> <td><?php echo $item->camp_fire_checkbox  ; echo $item->camp_fire_comments ;?> </td></tr>
      </tbody>
</table>
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
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
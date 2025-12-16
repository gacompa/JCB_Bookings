### JCB! Site View
# Path edit (path_edit)

## HTML:
```html
// No direct access to this file
defined('_JEXEC') or die;
// Get the application object.
$app = JFactory::getApplication();
// Get the JInput object.
$jinput = $app->input;
//Using getInt() ensures that the value is treated as a secure integer, which is crucial for preventing SQL injection and other vulnerabilities.
$itemId = $jinput->getInt('id');


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
<div class="bookings-location">
<?php echo $this->toolbar->render(); ?>
<form action="<?php echo Route::_('index.php?option=com_bookings&layout=edit&id='. (int) $this->item->id . $this->referral); ?>" method="post" name="adminForm" id="adminForm" class="form-validate" enctype="multipart/form-data">

<div class="main-card">

	<?php echo Html::_('uitab.startTabSet', 'locationTab', ['active' => 'details', 'recall' => true]); ?>

	<?php echo Html::_('uitab.addTab', 'locationTab', 'details', Text::_('COM_BOOKINGS_LOCATION_DETAILS', true)); ?>
		<div class="row">
			<div class="col-md-12">
				<?php echo LayoutHelper::render('location.details_left', $this); ?>
			</div>
		</div>
	<?php echo Html::_('uitab.endTab'); ?>

	<?php echo Html::_('uitab.addTab', 'locationTab', 'facilities', Text::_('COM_BOOKINGS_LOCATION_FACILITIES', true)); ?>
		<div class="row">
			<div class="col-md-12">
				<?php echo LayoutHelper::render('location.facilities_left', $this); ?>
			</div>
		</div>
	<?php echo Html::_('uitab.endTab'); ?>

	<?php $this->ignore_fieldsets = array('details','metadata','vdmmetadata','accesscontrol'); ?>
	<?php $this->tab_name = 'locationTab'; ?>
	<?php echo LayoutHelper::render('joomla.edit.params', $this); ?>

	<?php if ($this->canDo->get('location.edit.created_by') || $this->canDo->get('location.edit.created') || $this->canDo->get('location.edit.state') || ($this->canDo->get('location.delete') && $this->canDo->get('location.edit.state'))) : ?>
	<?php echo Html::_('uitab.addTab', 'locationTab', 'publishing', Text::_('COM_BOOKINGS_LOCATION_PUBLISHING', true)); ?>
		<div class="row">
			<div class="col-md-6">
				<?php echo LayoutHelper::render('location.publishing', $this); ?>
			</div>
			<div class="col-md-6">
				<?php echo LayoutHelper::render('location.publlshing', $this); ?>
			</div>
		</div>
	<?php echo Html::_('uitab.endTab'); ?>
	<?php endif; ?>

	<?php if ($this->canDo->get('core.admin')) : ?>
	<?php echo Html::_('uitab.addTab', 'locationTab', 'permissions', Text::_('COM_BOOKINGS_LOCATION_PERMISSION', true)); ?>
		<div class="row">
			<div class="col-md-12">
				<fieldset id="fieldset-rules" class="options-form">
					<legend><?php echo Text::_('COM_BOOKINGS_LOCATION_PERMISSION'); ?></legend>
					<div>
						<?php echo $this->form->getInput('rules'); ?>
					</div>
				</fieldset>
			</div>
		</div>
	<?php echo Html::_('uitab.endTab'); ?>
	<?php endif; ?>

	<?php echo Html::_('uitab.endTabSet'); ?>

	<div>
		<input type="hidden" name="task" value="location.edit" />
		<?php echo Html::_('form.token'); ?>
	</div>

<!-- this code block creates a pair of Save and Cancel buttons at the bottom of a form, with the Save button only appearing if the user has permission to save the data  -->
<form action="<?php echo Route::_('index.php?option=com_booking&task=trek.save'); ?>" method="post" class="form-validate">
<?php echo Html::_('uitab.endTabSet'); ?>
			<div class="control-group">
				<div class="controls">

 <?php $this->canSave=1 ; ?>
					<?php if ($this->canSave): ?>
						<button type="submit" class="validate btn btn-primary">
							<span class="fas fa-check" aria-hidden="true"></span>
							<?php echo Text::_('JSUBMIT'); ?>
						</button>
					<?php endif; ?>
					<a class="btn btn-danger"
					   href="<?php echo Route::_('index.php'); ?>"
					   title="<?php echo Text::_('JCANCEL'); ?>">
					   <span class="fas fa-times" aria-hidden="true"></span>
						<?php echo Text::_('JCANCEL'); ?>

					</a>
				</div>
			</div>
	<div>
</form>

	<?php echo Html::_('uitab.endTabSet'); ?>

	<div>
		<input type="hidden" name="task" value="location.save" />
		<?php echo Html::_('form.token'); ?>
	</div>
</form>
</div>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")
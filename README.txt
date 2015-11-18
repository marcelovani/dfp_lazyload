Module: DFP Lazyload

Description
===========
Experimental module to work with lazyloading.

Installation
============
Install as usual, clear caches

Configuration
=============

Documentation
=============
Example of implementation of add in javascript
...
var slot_machinename = Drupal.settings.dfpLazyload.config.dfp_lazyload_machinename;
var ad_slot = Drupal.settings.dfpLazyload.config.dfp_lazyload_rendered_slot;

// Append delta in order to clone slot multiple times.
var regex = new RegExp(slot_machinename, 'g');
ad_slot = ad_slot.replace(regex, slot_machinename + '_' + delta);

// Add slot to the page and render it.
$(selector).append( ad_slot );
googletag.pubads().refresh([googletag.slots[slot_machinename + '_' + delta]]);
...

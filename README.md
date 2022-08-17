# YSE Tacklebox

Hooks that apply to other modulesmedia_type_namecoach that we have to fish for.

## yse_tacklebox_entity_form_mode_alter

We want to isolate large groups of fields for the editor to make profile editing easier
We have form modes defined for entities that need them but without explicit hooks we cannot
present them as normal edit links.   We could pull in a huge inline form where we specify
the form mode, like we do with TICL paragraphs, but then you need a route and a menu and
training to avoid the edit button!  So instead we try to steer the appropriate form to the 
editor in the normal edit context.
Notes:
  - assume that permissions are being handled normally for read write
    - this means not checking for netid on entities if we confer ownership already
  - check for bundle to see if we need to act
  - check for conditions that governs the mode to use
    - on entity
    - with currentuser
    - environmental, etc.
 
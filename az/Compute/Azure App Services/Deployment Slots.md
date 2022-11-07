### Deployment Slots
	Live web apps with their own hostnames to transition a staged web app to the production slot.


### Settings Swapped During Transition
---
![[app_svc_nonslot_spec.png]]



### Settings Not Swapped During Transition
---
![[app_svc_slot_spec.png]]

### Deployment Slots Nuances
---
> - *Traffic can be redirected to 1+ deployment slots that are not the production slot.*
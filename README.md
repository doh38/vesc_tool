# VESC_TOOL for new PAS app Ebike firmware 
![Screenshot from 2023-07-25 21-04-25](https://github.com/doh38/bldc/assets/42808575/02c4454c-d68e-40b2-ac1a-39794b5f5d9a)

This is a better implementation of the PAS_app, it includes:
- 3 wire pas support
- 4 wires (quadrature) support
- 4 wires with torque sensor by hall dephasing support 
- 3&4 wires + torque sensor come in a few (WIP right now and will first use the throttle input)
- new PAS handlings (BASIC, HALL TORQUE, CADENCE, TORQUE SENSOR, CAN TORUE SENSOR)
- speed limit (little PID) in the PAS app which use current to reduce speed (I ditched the rpm ratio thing as it was unreliable and too complicated) 
- external speed sensor speed support
- brake support (especially for mid motors right now) with separated ramping 
- faster PAS which takes pedal rpm to calculate time out
- Modified adc-pas implementation to re-route adc in the pas app (and benefit from adc setup but also from speed limit)
- Most of the settings/parameters are accessible in LISP
- And of course full Eggrider suppor (Fw 2.7+ so you will need to wait or contact us directly), with level of assist, speed limit change per assist level, standard power/current/regen...etc settings directly from app (similar to what we have for ASI right now)
- Specific HW conf for the FS-75200 (which is one of my test VESC)

All of this is totally WIP right now, but should stable really soon. 
Updates will be referenced here.



# VESC® Tool

This is the source code of VESC Tool. A pre-compiled binary of both the stable release as well as the development release packaged with all the matching firmware for all supported hardware can be downloaded at http://vesc-project.com/

The stable binary is available for **Linux**, **Windows**, **MacOS**, **Android** and **iOS**. The development binary is available for **Linux**, **Windows** and **Android** and is updated every few days.

All binaries can also be downloaded free-of-charge for all platforms except for iOS, which only is available via the Apple App Store as they do not allow any other distribution channel.

## Code Contribution, Distribution and Trademark Usage

VESC is a registered trademark of Benjamin Vedder. Read the [trademark policies](https://vesc-project.com/trademark_policies) for more information.

The "official" binary release of VESC Tool is done via VESC Project only, as that gives users a way to verify that releases, that use the registered VESC trademark, originate from the VESC Project. It is not ok to host a binary release on a different channel and use the VESC trademark for that release.

It is ok to use the github fork function to make contributions to the code. That is because 1) it is the most convenient way to make contributions and 2) the forked repository states clearly that it is a fork and points back to the main repository where the original code can be found. Further, it is easy to see what the code changes are from the forked repository compared to the main repository via github, but that information is lost in a binary release.

Forks of VESC Tool on github are not encouraged to provide a binary release in the repository. That is because there is no way to tell the final binary apart from the official release once downloaded. Further, packaging the firmware, which has to be done as an additional step from a different repository, also cannot be verified whether it is done correctly.

**Forks without branding**  

Because the topic came up, here are some words about forking VESC Tool and removing the branding.  

If you make a fork of VESC Tool and remove all traces of the VESC trademark you are not breaking the trademark policies, but we still do not encourage that. The reason is that such forks are 1) confusing to users and 2) divert users away from the VESC Project itself and take away the opportunity to learn about it and to make donations if they choose to. For example, the majority of VESC donations today come from VESC Tool downloads.  

If you see a missing feature and you want to put in some work and make that feature available, we would appreciate if you contribute that back to the main VESC repositories. That way there is only one consistent and compatible release for everyone that is managed by the main authors of the VESC code who make the vast majority of the development. It also gives the main authors, who are the most familiar with the code, a chance to review features to make sure that they are as safe as possible and don't break other parts of the functionality.

## Add Your Hardware to the Binary Release

If you have custom hardware and you want to add support for it in the official release of VESC Tool, you can use the following steps:

1) Go to https://github.com/vedderb/bldc and use the github fork function.  
2) Make your changes, test them and make a pull request to the main repository.  
3) If the pull request gets accepted your hardware will become part of the next official release. It will show up in the binary beta typically after a few days and in the stable version the next time a stable release is made.

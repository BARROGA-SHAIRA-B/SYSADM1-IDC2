+----------------------------------+------------------------+----------+
| ![](vertopal_                    |                        |          |
| b3fcbfa34bae406b9b30e8853c62615b |                        |          |
| /media/image1.png){width="2.4in" |                        |          |
| height="0.5881944444444445in"}   |                        |          |
|                                  |                        |          |
| SCHOOL OF INFORMATION AND        |                        |          |
| TECHNOLOGY                       |                        |          |
+----------------------------------+------------------------+----------+
| NAME: Barroga, Shaira B.         | DATE PERFORMED: Sept   |          |
|                                  | 12                     |          |
+----------------------------------+------------------------+----------+
| Section: IDC2                    | DATE SUBMITTED:        |          |
+----------------------------------+------------------------+----------+

# SYSADM1 -- Managing Services in Linux

# Requirement: 

-   A virtual machine running Linux

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image2.png){width="4.135416666666667in"
height="1.8020833333333333in"}

Complete this lab as follows:

1.  Use the service --status-all command to list all active and inactive
    services.

List down active and inactive services in the table below. Provide five
(5) services for each column.

  -----------------------------------------------------------------------
  **Active**                             **Inactive**
  -------------------------------------- --------------------------------
  alsa-utils                             anacron

  apparmor                               bluetooth

  apport                                 console-setup.sh

  cron                                   grub-common

  cups                                   keyboard-setup.sh
  -----------------------------------------------------------------------

SS:

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image3.png){width="4.986056430446194in"
height="2.4970177165354333in"}

2.  Start the Bluetooth service using the systemctl command.

Ex. sudo systemctl start httpd

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image4.png){width="4.359946412948381in"
height="1.1875in"}

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image5.png){width="7.027083333333334in"
height="0.20347222222222222in"}

3.  Check the status of the Bluetooth service. What is its status?

-   Bluetooth service is enabled but not active (dead)

SS:

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image6.png){width="6.960196850393701in"
height="2.9095417760279965in"}

1.  Check the status of the cups services. Since when was it running?

-   It was running since Thursday, September 12, 2024 at 8:58

SS:

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image7.png){width="6.4717443132108485in"
height="3.0871741032370954in"}

1.  Stop cups services.

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image8.png){width="6.917632327209099in"
height="0.2396172353455818in"}

2.  Verify if the service was stopped.

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image9.png){width="1.1980839895013122in"
height="0.2500349956255468in"}

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image10.png){width="7.027083333333334in"
height="3.339583333333333in"}

3.  Restart the cups services

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image11.png){width="7.027083333333334in"
height="0.22083333333333333in"}

4.  Verify if the service was restarted.

![](vertopal_b3fcbfa34bae406b9b30e8853c62615b/media/image12.png){width="7.027083333333334in"
height="3.1020833333333333in"}

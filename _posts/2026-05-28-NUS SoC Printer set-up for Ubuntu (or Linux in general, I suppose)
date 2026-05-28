As part of the pain points of reinstalling the entire OS, I had the pleasure to have to set up the printers on my laptop again. Fun!

NUS School of Computing does give me some pages of free printing (thanks) but what use would it be if you can't print? There is a [guide in SoC DocHub](https://dochub.comp.nus.edu.sg/cf/guides/printing/linux/smbclient) (VPN or on-campus access required), but the Linux section just mentions "oh, print using SAMBA", which is kinda... eh. Furthermore, the info is *ever so slightly* outdated (as of May 28, 2026); so here is how I set up mine to avoid 45 minutes of Google-searching pain that I had to do fighting SAMBA on Ubuntu 26.04.

(Also, a lot of the guides assume you are using Ubuntu 24.04 or earlier, which has more settings button compared to 26.04, so even more fun times for us...)

Note: The SAMBA print server is either `nts27b.res.nus.edu.sg` or `nts09b.res.nus.edu.sg`. I believe that the latter is only for staff and ?only for registered PCs; so just try the first one. The domain is either `nusstf` or `nusstu` depending on whether you have a staff or a student.

Required packages:
* `CUPS`
* `smbclient`
* I'm not sure if this is required, but I installed `python3-smbc` as well.

Steps to connect:
1. Install the required packages
2. Check that the printers are available: `smbclient -L //nts27b.res.nus.edu.sg -U <domain>/<NUSNET>` -- replace domain (nusstu/nusstf) and NUSNET ID accordingly
3. Make sure the CUPS service is running, and go to http://localhost:631/ for the CUPS dashboard
4. Navigate to Administration > Add Printer > Windows Printer via SAMBA
5. Use the following for the URI: `smb://<username>:<password>@<domain>/nts27b.res.nus.edu.sg/<printer-name>`
6. Configure the driver based on the printer; the list of printer makes and model is listed in [SoC DocHub](https://dochub.comp.nus.edu.sg/cf/guides/printing/print-queues) (and I hope it's updated; I just veered over to see my own printer model)
7. Test print! It should be configured by now.

Here is a list of the public printers as of the time of writing:
| Name of Print Queues            | Location of Printer                        | Model of Printer                          | Banner  |
|---------------------------------|--------------------------------------------|-------------------------------------------|---------|
| psc008   psc008-sx   psc008-nb  | COM1, Basement (outside Programming Lab 3) | LEXMARK MS821DN, A4 Postscript III        | Yes     |
| psc011   psc011-sx   psc011-nb  | COM1, Basement (outside Programming Lab 3) | LEXMARK MS821DN, A4 Postscript III        | Yes     |
| psts   psts-sx   psts-nb        | COM1, Level 1, Printer Area                | LEXMARK MS821DN, A4 Postscript III        | Yes     |
| pstsb   pstsb-sx   pstsb-nb     | COM1, Level 1, Printer Area                | LEXMARK MS821DN, A4 Postscript III        | Yes     |
| pstsc   pstsc-sx   pstsc-nb     | COM1, Level 1, Printer Area                | LEXMARK MS821DN, A4 Postscript III        | Yes     |
| cptsc   cptsc-dx                | COM1-01-06, Technical Services             | LEXMARK CS921DE, Colour A4 Postscript III | No      |
| cptsc-a3   cptsc-a3-dx          | COM1-01-06, Technical Services             | LEXMARK CS921DE, Colour A3 Postscript III | No      |
| psf204   psf204-sx              | COM4, Level 2, Printer Area (corridor)     | LEXMARK MS810, A4 Postscript III          | Yes     |

as a note, the `-sx` suffix is for single-sided printing, `-dx` is for duplex, and `-nb` is for no banner.


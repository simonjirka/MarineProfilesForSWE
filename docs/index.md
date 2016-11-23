---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---

# Marine Profiles of the OGC Sensor Web Enablement Standards

## Contents

<div class="trigger">
  {% for my_page in site.pages %}
    {% if my_page.title %}
    <div>
      <a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.title | escape }}</a>
    </div>
    {% endif %}
  {% endfor %}
</div>
<br/>


## Acknowledgements

The profiles defined in this document have been developed within a series of research projects including:
* AODN
* BRIDGES
* ENVRIplus
* EUROFLEETS/EUROFLEETS2
* FixO<sup>3</sup>
* FRAM
* IOOS
* Jerico/Jerico-Next
* NeXOS
* ODIP/ODIP 2
* RITMARE
* SeaDataNet
* SenseOcean
* X-DOMES

![EC Logo](images/ec.png)


**BRIDGES** (Bringing together Industry for the Development of Glider Environment) is funded by the Horizon 2020 Framework Programme for Research and Innovation (H2020-BG-2014-2) of the European Union under grant agreement number 635359.

**FixO<sup>3</sup>** (Fixed Point Open Ocean Observatories Network) is funded by the Sevents Framework Programme (FP7) for Research and Innovation (FP7-INFRASTRUCTURES-2012-1-RTD) of the European Union under grant agreement number 312463.

**NeXOS** (Next generation, Cost-effective, Compact, Multifunctional Web Enabled Ocean Sensor Systems Empowering Marine, Maritime and Fisheries Management) is funded by the Sevents Framework Programme (FP7) for Research and Innovation (FP7-OCEAN-2013) of the European Union under grant agreement number 614102.

**ODIP 2** (Extending the Ocean Data Interoperability Platform) is funded by the Horizon 2020 Framework Programme for Research and Innovation (H2020-INFRASUPP-2014-2) of the European Union under grant agreement number 654310.

**TODO: ADD FURTHER Acknowledgements**

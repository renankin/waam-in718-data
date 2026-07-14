## About

This repository is meant to reproduce the tensile curves and infrared imaging data obtained in the paper:

> **Wire-arc directed energy deposition of Inconel 718: Effects of heat input and build interruptions on mechanical performance** \
R.M. Kindermann, M.J. Roy, R. Morana, J.A. Francis, P.B. Prangnel \
Additive Manufacturing, Volume 76, 2023, 103765, ISSN 2214-8604 \
https://doi.org/10.1016/j.addma.2023.103765

If you have used the data contained within this repository, please cite the main work.

## Repository structure

- `CSV_export_tensile` — tensile stress/strain data (see "Tensile tests" below)
- `CSV_export_pointTemp` — point temperature data (see "Temperature measurements" below)
- `CSV_export_resTimes` — residence time data (see "Temperature measurements" below)

## Tensile tests

The tensile testing was recorded using Digital Image Correlation (DIC). The results of the tests have been analysed using MATLAB, where the mapping of the tensile strain across the sample surface has been exported to MATLAB matrices.

Due to the large size of files, the tensile curves have been exported directly to CSV files for ease of use.

The tensile data is located in the `CSV_export_tensile` folder, where each file represents a tensile specimen. The header of the files contains true stress and strain, engineering stress and strain, and work hardening rate.

The following sample ID description has been used in the tests that preceded the paper, which can then be converted to conditions described in the paper:

<table>
  <thead>
    <tr>
      <th>Sample ID</th>
      <th>Travel speed (m/min)</th>
      <th>Process mode</th>
      <th>Interpass control</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>#19</td>
      <td>0.4</td>
      <td>CMT</td>
      <td>80°C</td>
    </tr>
    <tr>
      <td>#22</td>
      <td>1.0</td>
      <td>CMT</td>
      <td>80°C</td>
    </tr>
    <tr>
      <td>#36</td>
      <td>1.0</td>
      <td>GMAW-P</td>
      <td>30 s</td>
    </tr>
    <tr>
      <td>#37</td>
      <td>1.0</td>
      <td>CMT</td>
      <td>30 s</td>
    </tr>
    <tr>
      <td>#40</td>
      <td>0.4</td>
      <td>CMT</td>
      <td>30 s</td>
    </tr>
    <tr>
      <td>#42</td>
      <td>0.4</td>
      <td>GMAW-P</td>
      <td>30 s</td>
    </tr>
  </tbody>
</table>

Further to that, the samples have been tested in the as-deposited condition (AS) and in the longitudinal (L) and transverse (T) orientation relative to travel direction.

So, the labelling on the sample would be, e.g. `AS-L1#19`, which corresponds to the first longitudinal tensile specimen from the wall sample deposited with CMT process at 0.4 m/min using interpass temperature control of 80 °C.

## Temperature measurements

The folders `CSV_export_pointTemp` and `CSV_export_resTimes` are meant to reproduce Figures 7 and 8 in the paper, respectively. These figures show the mean build temperature at a defined position along the build height, and the residence times at which the temperature stays in the range for precipitation of gamma prime and gamma double prime phases.

In the data, the point temperatures were obtained at a position of 55 mm in the build height, between layers 2 and either 100 or 60, depending on the travel speed.

So, for example, `Plate#36_L2-110_pos55.csv` would be the file from sample #36 recorded between layers 2 and 110, captured at a build height of 55 mm.

In addition to the regular builds described in the table above, some other builds were stopped mid-build to analyse the effect of this on the temperature response.

The following table shows the additional tests which were done with varying build interruptions mid-build:

<table>
  <thead>
    <tr>
      <th>Sample ID</th>
      <th>Travel speed (m/min)</th>
      <th>Process mode</th>
      <th>Interpass control</th>
      <th>Build interruptions</th>
    </tr>
  </thead>
  <tbody>
      <tr>
      <td>#12</td>
      <td>1.0</td>
      <td>GMAW-P</td>
      <td>30 s</td>
      <td>1</td>
    </tr>
    <tr>
      <td>#13</td>
      <td>1.0</td>
      <td>CMT</td>
      <td>30 s</td>
      <td>1</td>
    </tr>
    <tr>
      <td>#38</td>
      <td>1.0</td>
      <td>CMT</td>
      <td>30 s</td>
      <td>3</td>
    </tr>
    <tr>
      <td>#39</td>
      <td>1.0</td>
      <td>GMAW-P</td>
      <td>30 s</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
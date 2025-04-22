
# Drop rebound at low Weber number

This repository provides MATLAB scripts for simulating the dynamics of liquid droplets impacting solid substrates. The code systematically explores droplet deformation, spreading, rebound behaviors, and other key physical phenomena, capturing detailed dynamics through numerical simulations.

![Rebound](bounce.png)

---

## Overview

The project models the complex behavior of liquid droplets when they impact solid surfaces, capturing phenomena like maximum spreading, bounce optimization, energy transfer, and shape deformation using a numerical approach based on spherical harmonics and Newton-Raphson methods. It includes simulation sweeps for parameter exploration such as Weber number (`We`), Bond number (`Bo`), and Ohnesorge number (`Oh`).

<table align="center">
  <tr>
    <td align="center">
      <figure>
        <img src="Supplemental movies/Movie 1.gif" alt="Image 1" width="50%"/> <br/>
        <em>Caption 1</em>
      </figure>    
    </td>
    <td align="center">
      <figure>
        <img src="Supplemental movies/Movie 2.gif" alt="Image 1" width="50%"/> <br/>
        <em>Caption 2</em>
      </figure>    
    </td>
  </tr>
  <tr>
    <td align="center">
      <figure>
        <img src="Supplemental movies/Movie 3.gif" alt="Image 1" width="50%"/> <br/>
        <figcaption>Caption 3</figcaption>
      </figure>    
    </td>
    <td align="center">
      <figure>
        <img src="Supplemental movies/Movie 4.gif" alt="Image 1" width="50%"/> <br/>
        <figcaption>Caption 4</figcaption>
      </figure>    
    </td>
  </tr>
</table>

---

# MATLAB Code


MATLAB R2020 or newer recommended (Parallel Computing Toolbox required). A python version of this solver is available at [this repo](https://github.com/Katiekuehr/Drop_Simulations)


## File Structure

```
project/
│
├── 1_code/
│   ├── sweeper_experiments.m
│   ├── simulation_code/
│   │   ├── function_to_minimize_v1.m
│   │   ├── maximum_contact_radius.m
│   │   ├── r_from_spherical.m
│   │   └── ...
│   └── postprocessing.m
├── 2_output/
│   ├── Logger/
│   └── (simulation results stored here)
└── 0_data/
    └── (processed data and logs)
```

---

## Running Simulations

You can run simulations in bulk or one by one
### Running in bulk:


In `sweeper_experiments.m`, set parameters like:
- Surface tension (`sigma`)
- Droplet density (`rho`)
- Initial radius (`Ro`)
- Weber (`We`) and Bond (`Bo`) numbers

Then, run the script. It should run them in parallel by default.

### Runnning only one simulation

The script `simulation_code/solve_motion_v2` can run single simulations. 

### Postprocessing simulations

Once simulations are completed, execute post-processing scripts to analyze simulation outcomes:

```matlab
postprocessing
```

This script computes metrics such as maximum droplet width, restitution coefficients, and contact times.

### Generate Animations (Optional):

   Create animations from the simulation data:

   ```matlab
   export_animation
   ```

---


---

## Cite Me

If you use this software or refer to the methodologies in your academic or professional work, please cite our associated paper as follows:

```bibtex
to be completed
```

---

## License

This software is provided under the [MIT License](LICENSE). See the `LICENSE` file for more details.

# rabi-oscillation

Imagine one shoots an electromagnetic (EM) wave of a specific wavelength using such as lasers to a system consisting of a ground state and an excited state. If it happens that the energy of the EM wave resonates with the energy gap between the ground state and the first excited state, then the electrons in the ground state would absorb the incoming EM wave and jumps up to the first excited state. Being in the excited state, the photons or EM waves passing through would keep travelling, however if the system de-excites, it will produce a photon with the same energy as the energy gap and the same phase as the shot EM wave. This phenomenon is called stimulated emission. The electron or system would then keep oscillating between the ground state and the excited state periodically with a certain frequency called the Rabi Frequency and thus the oscillation process is named as “Rabi Oscillation” [1].

<p align="center">

<img width="972" alt="Screenshot 2022-12-27 at 6 56 46 PM" src="https://user-images.githubusercontent.com/103773281/209663275-963e68ec-0c66-4cab-b63d-aca8715e6956.png">
  <p align="center">
  Figure 1. Absorption of a photon (Left) and Stimulated Emission (Right)
  </p>
</p>

Mathematically, the Rabi oscillation could be described by a periodical Hamiltonian of a simple two- level system such as the following shows

<p align="center">

  <img width="200" alt="Screenshot 2022-12-27 at 10 57 35 PM" src="https://user-images.githubusercontent.com/103773281/209690794-a900ae66-6a37-40b6-9c62-b03a71107d5e.png">

</p>

with $\ \frac{1}{2} \hbar \omega$ and $\ - \frac{1}{2} \hbar \omega$ as the excited and ground sate energy respectively, 𝐸 as the overall inference
from the applied light and thus the product of the amplitude of the electric field and coupling strength between the light and atom, and 𝜔 is the angular frequency of the incoming light. Thus, our goal is to solve for the wavefunction of the ground and excited states from the Schrodinger equation which states that,

<p align="center">
  $\ i\hbar \frac{d}{dt} \ket{\psi (t)} = \hat{H} \ket{\psi (t)}$
  </p>
  
where $\ \ket{\psi (t)}$ equals to,
<p align="center">

  <img width="150" alt="Screenshot 2022-12-27 at 11 11 52 PM" src="https://user-images.githubusercontent.com/103773281/209692370-5b843803-798e-432f-98df-78e991a025cb.png">
 
  </p>
  
in which $\ \psi_{\uparrow}(t)$ corresponds to the wavefunction of the electron in the excited state while $\ \psi_{\downarrow}(t)$ signifies the wavefunction of the electron in the ground state. Furthermore, notice that the Hamiltonian is periodical in time which tells us that $\ \hat{H}(t+T) = \hat{H}(t)$. This lets us to use what is called “Floquet Theorem” which states that the general solution of the Schrodinger equation above can be written as,

<p align="center">
  $\ \ket{\psi (t)} = \Sigma_{i=1}^n c_n \ket{\psi_i (t)}$
  </p>
  
 where $\ ket{\psi_i (t)}$ meaning is the $\ i$-th eigenstate out of $\ n$-many of them (where in our case $\ i$ = 1,2). Then, $\ \ket{\psi_i (t)}$ can be factorised into,
 
 <p align="center">
 <img width="124" alt="Screenshot 2022-12-27 at 11 22 56 PM" src="https://user-images.githubusercontent.com/103773281/209693609-e2b8d803-2b99-44d2-b2ea-8d516e616dbe.png">
  </p>
  
in which $\ \epsilon_i$ is called the quasi-energy with its values lies between $\ -\frac{\hbar \omega}{2} < \epsilon_i < \frac{\hbar \omega}{2}$ and $\ \ket{u_i (t)}$ is a periodical function so that $\ \ket{u_i (t+T} = \ket{u_i (t)}$. Plugging in Eq. (5) to the Schrodinger equation (Eq. (2)) would give us,

<p align="center">
  $\ \epsilon_i \ket{u_u (t)} = [\hat{H}(t) - i \hbar \frac{d}{dt}] \ket{u_i (t)}$
  </p>

Fortunately, due to this periodicity of $\ \ket{u_i(t)}$, one can expand it in a complex Fourier series and obtain the following equation,

<p align="center">
  
  <img width="156" alt="Screenshot 2022-12-27 at 11 44 08 PM" src="https://user-images.githubusercontent.com/103773281/209696100-02625e60-0027-48a9-b18f-ddbdd33a0d5f.png">

  </p>
  
where $\ \psi_{\uparrow, l, i}$ and $\ \psi_{\downarrow, l, i}$ are the $\ l$-th coefficient for the $\ l$-th term in the Fourier series for the excited and ground state respectively, $\ N$ is the cut-off value for the Fourier series, and $\ \omega_l = \frac{2 \pi l}{T} = l \omega$ which is the corresponding frequency for different terms in the Fourier series.


To further simplify the problem, the periodic Hamiltonian $\ (\hat{H} (t))$ would also be expanded in the complex Fourier series which then if we apply the Fourier transformation by multiplying it with $\ e^{il}$ and integrating it over the period, it will yield us the equation,

<p align = "center">
  $\ \epsilon_i \ket{\phi_{m,i}} = \Sigma_l [\hat{H} (\omega_m - \omega_n) + \hbar \omega_l \delta_{m,l}] \ket{\phi_{l,i}} = \Sigma_l \hat{H}_{m,l}^{Floquet} \ket{\phi_{l,i}}$
  </p>
  
Applying then the above equation and rearrangin the eigenvector of $\ \epsilon_i$ so that i becomes the following column vector,

<p align="center">
 <img width="64" alt="Screenshot 2022-12-27 at 11 50 39 PM" src="https://user-images.githubusercontent.com/103773281/209697034-e9de7d1f-3171-4cb6-92dd-fd1d8a10c804.png">
  </p>
  
 with $\ 2(2N+1)$ number of rows, allows us to write down the Floquet Hamiltonian matrix as the following form,
 
 
<p align="center">
<img width="435" alt="Screenshot 2022-12-27 at 11 51 30 PM" src="https://user-images.githubusercontent.com/103773281/209697152-46f709d9-3fc1-4fe8-b7e0-4d55df8ad46c.png">
  
  </p>
  
 which has the dimension of $\ 2(2N+1) \times 2(2N+1)$ . Solving the above eigenvalue problem would then give us the general solution of the wavefunction in the form of
 
 <p align="center">
  
  <img width="316" alt="Screenshot 2022-12-27 at 11 55 20 PM" src="https://user-images.githubusercontent.com/103773281/209697590-106af6e0-8fb6-4f04-bf08-a161ddcd4710.png">

  
  </p>
 
 which allows us to finally obtain the general wavefunction.

## Libraries Used
* NumPy
* Matplotlib

## Results and Analysis

## References

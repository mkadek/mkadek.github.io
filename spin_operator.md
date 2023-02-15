# Many-electron spin operator in second quantization

## Square of the spin

Many-electron spin operator can be constructed from one-electron spin operatos as
$$
\pmb{S} = \sum_{i=1}^N \pmb{s}_i,
$$
where $\pmb{s}_i = \pmb{\sigma}_i/2$ when $\hbar=1$ units are used.

$S^2$ can then be calculated as
$$
S^2 = S_x^2 + S_y^2 + S_z^2.
$$
Note that $S^2$ cannot be calculated as a sum of one-electron operators, *i.e.* is not *bilinear* in terms of fermionic creation and annihilation operators $a^{\dagger}_P,a_P$.

We can define
$$
S_{+} = S_x + i S_y\\
S_{-} = S_x - i S_y
$$
to get
$$
S^2 = \frac{1}{2}\Big(S_{+}S_{-} + S_{-}S_{+}\Big) + S_z^2.
$$
Using ($u,v = x,y,z$)
$$
\big[S_u,S_v\big] = i\varepsilon_{uvw} S_w
$$
to eliminate either of the $S_{+}S_{-}$ or $S_{-}S_{+}$ terms, gives
$$
S^2 = S_{\pm}S_{\mp} \mp S_z + S_z^2.
$$



## Spin in second quantization

### General theory

Let $P,Q,\ldots$ denote spin-orbitals, $p,q,\ldots$ denote spatial orbitals, and $\alpha, \beta, \ldots$ denote spin indices. The one- and two-electron reduced density matrices (1RDM and 2RDM) are defined as
$$
\gamma_{PQ} = \langle\Psi|a^{\dagger}_Qa_P|\Psi\rangle,\\
\Gamma_{PQRS} = \langle\Psi|a^{\dagger}_Ra^{\dagger}_Sa_Qa_P|\Psi\rangle.
$$
The total spin in the second quantization is expressed as
$$
\pmb{S} = \sum_{PQ} \pmb{S}_{PQ} a^{\dagger}_P a_Q,
$$
where
$$
\pmb{S}_{PQ} = \int \phi^{\dagger}_P(\pmb{r})\pmb{s} \phi_Q(\pmb{r}) d^3\pmb{r}.
$$
While the integration is over spatial coordinates in 3D, $\phi_P$ are still two-component spinors, in general, and inner products (to contract the spin degrees of freedom) are carried out with the $2\times 2$ matrix $\pmb{s}$. Using 1RDM, the expectation value of $\pmb{S}$ is then
$$
\langle\pmb{S}\rangle = \sum_{PQ} \pmb{S}_{PQ}\gamma_{QP} \equiv \mathrm{Tr}(\pmb{S}\gamma)
$$

### Restricted formalism

Let's assume
- nonrelativistic spin-restricted formalism
- orthonormal set of molecular (spin-)orbitals
- $P\equiv p\alpha$, $Q\equiv q\beta$
- $\alpha,\beta = \uparrow,\downarrow$

Then
$$
\pmb{S}_{p\alpha,q\beta} = \delta_{pq} \pmb{s}_{\alpha\beta},
$$
and
$$
\pmb{S} = \sum_p \begin{pmatrix}a^{\dagger}_{p\uparrow} & a^{\dagger}_{p\downarrow}\end{pmatrix} \pmb{s} \begin{pmatrix}a_{p\uparrow} \\ a_{p\downarrow}\end{pmatrix}.
$$
Note the relationship with the [Bogoliubov transformation](https://en.wikipedia.org/wiki/Bogoliubov_transformation), for $a^{\dagger}_{\uparrow}\equiv a^{\dagger}$ and $a^{\dagger}_{\downarrow}\equiv b^{\dagger}$ if we replace $\pmb{S}$ with the Hamiltonian.

#### $S_z$ projection

For the $S_z$ projection, we obtain
$$
S_z = \frac{1}{2} \sum_p a^{\dagger}_{p\uparrow}a_{p\uparrow} - a^{\dagger}_{p\downarrow}a_{p\downarrow}.
$$
It is clear that the expectation value of $S_z$ measures the number of "up" electrons minus the number of "down" electrons. However, this can also be obtained using the 1RDM as
$$
\langle S_z\rangle = \frac{1}{2}\mathrm{Tr}\begin{pmatrix} 1 & 0\\
0 & -1\end{pmatrix} \begin{pmatrix} \gamma_{\uparrow\uparrow} & \gamma_{\uparrow\downarrow} \\
\gamma_{\downarrow\uparrow} & \gamma_{\downarrow\downarrow}
\end{pmatrix} = \frac{N_{\uparrow} - N_{\downarrow}}{2}.
$$
It can also be seen, that (for the restricted case)
$$
\langle S_z^2\rangle = \langle S_z\rangle^2.
$$
If the number of "up" and "down" electrons is equal, then both $S_z$ and its square will be zero.

#### Spin raising and lowering

It follows that
$$
S_{+} = \sum_p a^{\dagger}_{p\uparrow} a_{p\downarrow}\\
S_{-} = \sum_p a^{\dagger}_{p\downarrow} a_{p\uparrow}
$$
Thus
$$
S_{+}S_{-} = \sum_{pq} a^{\dagger}_{p\uparrow} a_{p\downarrow} a^{\dagger}_{q\downarrow} a_{q\uparrow},
$$
which gives
$$
S_{+}S_{-} = N_{\uparrow} - \sum_{pq} a^{\dagger}_{p\uparrow} a^{\dagger}_{q\downarrow} a_{p\downarrow} a_{q\uparrow}
$$

#### Spin square revisited

We can combine the expression for the $S^2$ that uses $S_{\pm}$ with the second-quantized formes:
$$
S^2 = - \sum_{pq} a^{\dagger}_{p\uparrow} a^{\dagger}_{q\downarrow} a_{p\downarrow} a_{q\uparrow} + N_{\uparrow} + S_z(S_z-1),
$$
and, for the expectation value
$$
\langle S^2\rangle = - \sum_{pq} \Gamma_{p\uparrow q\downarrow q\uparrow p\downarrow} + \frac{N_{\uparrow}+N_{\downarrow}}{2} + \left(\frac{N_{\uparrow}-N_{\downarrow}}{2}\right)^2
$$

Note, that the definition of the 2RDM from the [Pink Book](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) (aka "The Bible")
$$
\bar{\Gamma}_{PQRS} = \langle\Psi|a^{\dagger}_Pa^{\dagger}_Ra_Sa_Q|\Psi\rangle,
$$
differs from $\Gamma$, i.e.
$$
\Gamma_{PQRS} = \bar{\Gamma}_{RPSQ}.
$$
Then
$$
\langle S^2\rangle = - \sum_{pq} \bar{\Gamma}_{p\uparrow q\uparrow q\downarrow p\downarrow} + \frac{N_{\uparrow}+N_{\downarrow}}{2} + \left(\frac{N_{\uparrow}-N_{\downarrow}}{2}\right)^2
$$

#### HF and DFT case

If the reference state $|\Psi\rangle$ is a single Slater determinant, then the 2RDM can be written in terms of 1RDM as
$$
\Gamma_{PQRS} = \gamma_{PR}\gamma_{QS} - \gamma_{PS}\gamma_{QR}.
$$
Since $\gamma_{PQ} = f_P\delta_{PQ}$, where $f_P$ is the occupation number of the spin-orbital, we can write
$$
\sum_{pq} \Gamma_{p\uparrow q\downarrow q\uparrow p\downarrow} = \sum_p f_{p\uparrow}f_{p\downarrow} = \frac{N_{\uparrow}+N_{\downarrow}}{2},
$$
where we assumed double occupancy of orbitals, i.e. the sum counts the number of occupied orbitals, which is half of the electron number. Since we also have $N_{\uparrow} = N_{\downarrow}$ in this case, we get
$$
\langle S^2\rangle = 0,
$$
which is expected for restricted HF and DFT wave functions.

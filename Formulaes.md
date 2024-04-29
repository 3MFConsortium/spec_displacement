# LaTex formulaes for creating the images files

$$
    \begin{split}
        p_1 = p(u_1, v_1) \\
        p_2 = p(u_2, v_2) \\
        p_3 = p(u_3, v_3)
    \end{split}
$$

...

$$ \tilde{p}(u, v) = p(u, v) + d(u, v) \cdot f(u, v) \cdot n(u, v) $$

...

$$ d(u,v) =  \begin{cases}
    texture(u,v) * height + offset & \text{$(\mathtt{TILE}_u \neq \mathtt{NONE}$ or $0 \leq u \leq 1$) and} \\
     & \text{$(\mathtt{TILE}_v \neq \mathtt{NONE}$ or $0 \leq v \leq 1$)} \\
    0 & \mathrm{otherwise}\\
\end{cases}
$$

...

$$  P = \alpha_1 p_1 + \alpha_2 p_2 + \alpha_3 p_3 $$

...

$$ (u, v) = (\alpha_1u_1 + \alpha_2u_2 + \alpha_3u_3, \alpha_1v_1 + \alpha_2v_2 + \alpha_3v_3) $$

...

$$ n(u,v) = \frac{\alpha_1 n_1 + \alpha_2 n_2 + \alpha_3 n_3}{\|\alpha_1 n_1 + \alpha_2 n_2 + \alpha_3 n_3\|} $$

...

$$ f(u,v) = \alpha_1 f_1 + \alpha_2 f_2 + \alpha_3 f_3 $$

...

$$ (u, v) \longrightarrow (i_c, j_c) = \big((1-v)\cdot H-0.5, u\cdot W-0.5\big) $$

...

$$
    \begin{array}{ll}
        i_0=\lfloor i_c\rfloor;&\qquad i_1=i_0+1\\
        j_0=\lfloor j_c\rfloor; &\qquad j_1=j_0+1\\
    \end{array}
$$

...

$$
    \begin{array}{rcl}
        \lambda_i&=&i_c-\lfloor i_c\rfloor\\
        \lambda_j&=&j_c-\lfloor j_c\rfloor\\
        texture(u,v) &=
            & C(i_0, j_0)(1-\lambda_i)(1-\lambda_j)+\\
            && C(i_0, j_1)(1-\lambda_i)\lambda_j+\\
            && C(i_1, j_0)\lambda_i(1-\lambda_j)+\\
            && C(i_1, j_1)\lambda_i\lambda_j
    \end{array}
$$

...

$$
	\begin{array}{rcl}
	\mathtt{CLAMP}(x, L)&=&\min\big(L-1, \max(x, 0)\big)\\
	\mathtt{WRAP}(x, L)&=& x - \Big\lfloor \frac{x}{L}\Big\rfloor\cdot L\\
	\mathtt{MIRROR}(x, L)&=&   \begin{cases}
		x - \Big\lfloor \frac{x}{L}\Big\rfloor\cdot L & \qquad\left\lfloor \frac{x}{L}\right\rfloor\equiv 0\,(\mathrm{mod~}2)\\ 
		\left(\Big\lfloor\frac{x}{L}\Big\rfloor+1\right)\cdot L - x -1& \qquad \mathrm{otherwise}\\
	\end{cases}\\
	\mathtt{NONE}(x, L)&=& x%\\
	\end{array}
$$

...

$$ C(i, j) =  \begin{cases}
    \mathtt{IMAGE}\big[\mathtt{TILE}_i(i, H)\big]\big[\mathtt{TILE}_j(j, W)\big] & \text{$(\mathtt{TILE}_i \neq \mathtt{NONE}$ or $0 \leq i < L$) and} \\
     & \text{$(\mathtt{TILE}_j \neq \mathtt{NONE}$ or $0 \leq j < L$)} \\
    0 & \mathrm{otherwise}\\
\end{cases}
$$



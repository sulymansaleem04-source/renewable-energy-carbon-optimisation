# Model specification

Technologies i: solar PV, wind, small hydro, gas (CCGT).

Decision variables: K_i (capacity, MW), g_i (generation, MWh per year).

Minimise total annual cost:
sum_i [ (c_i * CRF + F_i) * K_i + v_i * g_i ]
CRF = r(1+r)^L / ((1+r)^L - 1)

Subject to:
1. g_i <= CF_i * 8760 * K_i   (resource limit)
2. sum_i g_i >= D             (electricity demand)
3. sum_i e_i * g_i <= E       (carbon cap)
4. K_i, g_i >= 0

The dual value of constraint 3 is the shadow price of carbon.
LCOE_i = (c_i * CRF + F_i) / (CF_i * 8760) + v_i

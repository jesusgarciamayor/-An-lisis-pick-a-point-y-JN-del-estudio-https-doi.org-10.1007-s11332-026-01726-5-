# -An-lisis-pick-a-point-y-JN-del-estudio-https-doi.org-10.1007-s11332-026-01726-5-
Cardiorespiratory capacity as a moderator in the relationship between physical literacy and life satisfaction in primary and secondary physical education student
library(ggplot2)

# Figura final daltónicos Pick-a-Point

# Paleta de colores para daltónicos Pick-a-point
library(viridisLite)
library(ggplot2)
library(viridis)


# Total
total <- data.frame(
  PL = c(3.4103, 4.0014, 4.5924, 3.4103, 4.0014, 4.5924, 3.4103, 4.0014, 4.5924),
  PCF = c(2.5624, 2.5624, 2.5624, 3.6321, 3.6321, 3.6321, 4.7018, 4.7018, 4.7018),
  SWL = c(3.8788, 4.2712, 4.6637, 3.9657, 4.3009, 4.6362, 4.0526, 4.3306, 4.6086)
)

# GIRLS
girls <- data.frame(
  PL = c(3.3501, 3.8970, 4.4439, 3.3501, 3.8970, 4.4439, 3.3501, 3.8970, 4.4439),
  PCF = c(2.3438, 2.3438, 2.3438, 3.3641, 3.3641, 3.3641, 4.3845, 4.3845, 4.3845),
  SWL = c(3.9813, 4.3795, 4.7776, 3.7833, 4.2867, 4.7901, 3.5852, 4.1939, 4.8026)
)

# BOYS
boys <- data.frame(
  PL = c(3.4882, 4.1032, 4.7183, 3.4882, 4.1032, 4.7183, 3.4882, 4.1032, 4.7183),
  PCF = c(2.8403, 2.8403, 2.8403, 3.8934, 3.8934, 3.8934, 4.9466, 4.9466, 4.9466),
  SWL = c(3.7931, 4.0789, 4.3646, 4.1766, 4.2941, 4.4116, 4.5602, 4.5094, 4.4586)
)

# Crear los gráficos
gg_total <- ggplot(total, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_line() +
  geom_point() +
  labs(title = "Total") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

gg_girls <- ggplot(girls, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_line() +
  geom_point() +
  labs(title = "Girls") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

gg_boys <- ggplot(boys, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_line() +
  geom_point() +
  labs(title = "Boys") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

# Unir los gráficos
install.packages("patchwork")
library(patchwork)
combined_plot <- gg_total + gg_girls + gg_boys + plot_layout(guides = 'collect')

# Mostrar el gráfico combinado
combined_plot









# Figura final daltónicos J-N

#Paquetes y librerías necesarias

install.packages(viridisLite)
install.packages("viridis")
library(viridis)
library(ggplot2)
library(viridisLite)

install.packages("viridis")
library(viridis)

# Datos para chicos y chicas
data_boys <- data.frame(
  PCF = c(1.0000, 1.2000, 1.4000, 1.6000, 1.8000, 2.0000, 2.2000, 2.4000, 2.6000, 
          2.8000, 3.0000, 3.2000, 3.4000, 3.5902, 3.6000, 3.8000, 4.0000, 4.2000, 
          4.4000, 4.6000, 4.8000, 5.0000),
  Effect = c(0.9427, 0.8908, 0.8388, 0.7869, 0.7349, 0.6830, 0.6310, 0.5790, 0.5271, 
             0.4751, 0.4232, 0.3712, 0.3192, 0.2698, 0.2673, 0.2153, 0.1634, 0.1114, 
             0.0594, 0.0075, -0.0445, -0.0964),
  se = c(0.2295, 0.2151, 0.2012, 0.1880, 0.1757, 0.1643, 0.1541, 0.1454, 0.1385, 
         0.1337, 0.1310, 0.1308, 0.1330, 0.1372, 0.1375, 0.1440, 0.1524, 0.1623, 
         0.1735, 0.1857, 0.1988, 0.2125),
  t = c(4.1076, 4.1413, 4.1684, 4.1847, 4.1839, 4.1574, 4.0941, 3.9810, 3.8046, 
        3.5547, 3.2293, 2.8376, 2.4003, 1.9665, 1.9442, 1.4949, 1.0719, -0.6864, 
        -0.3427, -0.0403, -0.2238, -0.4538),
  p = c(0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0001, 0.0001, 0.0002, 
        0.0004, 0.0014, 0.0048, 0.0169, 0.0500, 0.0527, 0.1358, 0.2845, 0.4929, 
        0.7321, 0.9679, 0.8231, 0.6503),
  LLCI = c(0.4914, 0.4678, 0.4431, 0.4171, 0.3895, 0.3599, 0.3279, 0.2930, 0.2546, 
           0.2123, 0.1655, 0.1139, 0.0577, 0.0000, -0.0031, -0.0679, -0.1364, -0.2078, 
           -0.2817, -0.3577, -0.4353, -0.5143),
  ULCI = c(1.3941, 1.3138, 1.2346, 1.1567, 1.0803, 1.0060, 0.9341, 0.8651, 0.7995, 
           0.7380, 0.6808, 0.6285, 0.5808, 0.5397, 0.5376, 0.4986, 0.4631, 0.4306, 
           0.4006, 0.3727, 0.3464, 0.3215)
)

data_girls <- data.frame(
  PCF = c(1.0000, 1.0982, 1.2000, 1.4000, 1.6000, 1.8000, 2.0000, 2.2000, 2.4000, 2.6000, 
          2.8000, 3.0000, 3.2000, 3.4000, 3.6000, 3.8000, 4.0000, 4.2000, 4.4000, 4.6000, 
          4.8000, 5.0000),
  Effect = c(0.4745, 0.4930, 0.5122, 0.5499, 0.5877, 0.6254, 0.6631, 0.7009, 0.7386, 0.7763, 
             0.8141, 0.8518, 0.8895, 0.9273, 0.9650, 1.0027, 1.0405, 1.0782, 1.1159, 1.1537, 
             1.1914, 1.2291),
  se = c(0.2595, 0.2507, 0.2417, 0.2243, 0.2074, 0.1913, 0.1760, 0.1619, 0.1492, 0.1383, 
         0.1297, 0.1239, 0.1213, 0.1221, 0.1262, 0.1333, 0.1430, 0.1548, 0.1682, 0.1829, 
         0.1986, 0.2151),
  t = c(1.8287, 1.9667, 2.1196, 2.4520, 2.8329, 3.2693, 3.7673, 4.3298, 4.9517, 5.6137, 
        6.2753, 6.8726, 7.3310, 7.5932, 7.6454, 7.5203, 7.2750, 6.9657, 6.6345, 6.3075, 
        5.9988, 5.7145),
  p = c(0.0683, 0.0500, 0.0347, 0.0147, 0.0049, 0.0012, 0.0002, 0.0000, 0.0000, 0.0000, 
        0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 0.0000, 
        0.0000, 0.0000),
  LLCI = c(-0.0358, 0.0000, 0.0369, 0.1088, 0.1797, 0.2492, 0.3170, 0.3825, 0.4452, 0.5044, 
           0.5589, 0.6081, 0.6509, 0.6871, 0.7168, 0.7405, 0.7592, 0.7738, 0.7851, 0.7940, 
           0.8008, 0.8061),
  ULCI = c(0.9848, 0.9860, 0.9875, 0.9910, 0.9957, 1.0016, 1.0093, 1.0192, 1.0320, 1.0483, 
           1.0692, 1.0956, 1.1282, 1.1675, 1.2132, 1.2650, 1.3218, 1.3826, 1.4467, 1.5134, 
           1.5820, 1.6522)
)

gg_girls <- ggplot(data_girls, aes(x = PCF, y = Effect, color = factor(p >= 0.05))) +
  geom_line() +
  geom_ribbon(aes(ymin = LLCI, ymax = ULCI), alpha = 0.2, linetype = 1) +
  geom_point() +
  scale_color_manual(values = palette, guide = "none") +
  labs(x = "PCF", y = "Effect") +
  ggtitle("Girls") +
  theme_minimal() +
  theme(panel.grid = element_blank(),
        panel.border = element_blank(),
        legend.position = "right",
        panel.grid.major = element_line(color = "lightgrey"))


gg_boys <- ggplot(data_boys, aes(x = PCF, y = Effect, color = factor(p >= 0.05))) +
  geom_line() +
  geom_ribbon(aes(ymin = LLCI, ymax = ULCI), alpha = 0.2, linetype = 1) +
  geom_point() +
  scale_color_manual(values = palette, guide = "none") +
  labs(x = "PCF", y = "Effect") +
  ggtitle("Boys") +
  theme_minimal() +
  theme(panel.grid = element_blank(),
        panel.border = element_blank(),
        legend.position = "right",
        panel.grid.major = element_line(color = "lightgrey"))



# Combinar gráficos
library(patchwork)
combined_plot <- gg_girls + gg_boys 

# Mostrar figura
combined_plot


# EDAD BOYS 8-12 YEARS OLD

# Cargar las librerías necesarias
library(viridis)
library(ggplot2)
library(patchwork)

# Datos proporcionados
data <- data.frame(
  PCF = c(1.0000, 1.2105, 1.4211, 1.6316, 1.8421, 2.0526, 2.1077, 2.2632, 2.4737, 2.6842, 2.8947, 
          3.1053, 3.3158, 3.5263, 3.7368, 3.8636, 3.9474, 4.1579, 4.3684, 4.5789, 4.7895, 5.0000),
  Effect = c(1.0031, 0.8938, 0.7845, 0.6753, 0.5660, 0.4567, 0.4281, 0.3475, 0.2382, 0.1289, 0.0197, 
             -0.0896, -0.1989, -0.3081, -0.4174, -0.4832, -0.5267, -0.6359, -0.7452, -0.8545, -0.9637, -1.0730),
  se = c(0.2938, 0.2757, 0.2589, 0.2436, 0.2303, 0.2192, 0.2166, 0.2106, 0.2049, 0.2024, 0.2032, 
         0.2071, 0.2142, 0.2239, 0.2361, 0.2445, 0.2504, 0.2664, 0.2838, 0.3024, 0.3220, 0.3425),
  t = c(3.4140, 3.2419, 3.0304, 2.7715, 2.4578, 2.0841, 1.9762, 1.6500, 1.1624, 0.6370, 0.0968, 
        -0.4325, -0.9286, -1.3760, -1.7677, -1.9762, -2.1034, -2.3873, -2.6256, -2.8252, -2.9925, -3.1331),
  p = c(0.0008, 0.0015, 0.0029, 0.0063, 0.0151, 0.0389, 0.0500, 0.1011, 0.2470, 0.5251, 0.9230, 
        0.6660, 0.3546, 0.1709, 0.0792, 0.0500, 0.0371, 0.0182, 0.0096, 0.0054, 0.0032, 0.0021),
  LLCI = c(0.4224, 0.3490, 0.2729, 0.1938, 0.1109, 0.0236, 0.0000, -0.0687, -0.1668, -0.2711, -0.3818, 
           -0.4989, -0.6221, -0.7507, -0.8840, -0.9663, -1.0215, -1.1624, -1.3061, -1.4521, -1.6002, -1.7498),
  ULCI = c(1.5837, 1.4387, 1.2962, 1.1568, 1.0211, 0.8898, 0.8563, 0.7637, 0.6432, 0.5290, 0.4212, 
           0.3198, 0.2244, 0.1344, 0.0492, 0.0000, -0.0318, -0.1095, -0.1843, -0.2568, -0.3273, -0.3962)
)

# Crear el gráfico
gg <- ggplot(data, aes(x = PCF, y = Effect, color = factor(p >= 0.05))) +
  geom_line() +
  geom_ribbon(aes(ymin = LLCI, ymax = ULCI), alpha = 0.2, linetype = 1) +
  geom_point() +
  scale_color_manual(values = viridis(2), guide = "none") +
  labs(x = "PCF", y = "Effect") +
  ggtitle("Boys 8-12 years old") +
  theme_minimal() +
  theme(panel.grid = element_blank(),
        panel.border = element_blank(),
        legend.position = "right",
        panel.grid.major = element_line(color = "lightgrey"))

# Mostrar el gráfico
print(gg)







Edad


# Asegúrate de que las librerías necesarias están cargadas
library(ggplot2)
library(viridis)
library(patchwork)

# Crear los data frames con los datos proporcionados

# Datos de "Girls 8-12 years old"
girls_8_12 <- data.frame(
  PL = c(3.5374, 4.0259, 4.5143, 3.5374, 4.0259, 4.5143, 3.5374, 4.0259, 4.5143),
  PCF = c(2.5002, 2.5002, 2.5002, 3.4914, 3.4914, 3.4914, 4.4826, 4.4826, 4.4826),
  SWL = c(4.0009, 4.3283, 4.6557, 4.6009, 4.8068, 5.0127, 5.2009, 5.2853, 5.3698)
)

# Datos de "Boys 8-12 years old"
boys_8_12 <- data.frame(
  PL = c(3.3786, 4.0692, 4.7597, 3.3786, 4.0692, 4.7597, 3.3786, 4.0692, 4.7597),
  PCF = c(2.6858, 2.6858, 2.6858, 3.8543, 3.8543, 3.8543, 5.0000, 5.0000, 5.0000),
  SWL = c(4.0613, 4.1497, 4.2382, 4.6904, 4.3601, 4.0298, 5.3074, 4.5664, 3.8255)
)

# Datos de "Girls 13-18 years old"
girls_13_18 <- data.frame(
  PL = c(3.2716, 3.8349, 4.3983, 3.2716, 3.8349, 4.3983, 3.2716, 3.8349, 4.3983),
  PCF = c(2.2724, 2.2724, 2.2724, 3.3029, 3.3029, 3.3029, 4.3335, 4.3335, 4.3335),
  SWL = c(3.9339, 4.4852, 5.0365, 3.4512, 4.0849, 4.7186, 2.9686, 3.6847, 4.4008)
)

# Datos de "Boys 13-18 years old"
boys_13_18 <- data.frame(
  PL = c(3.5707, 4.1271, 4.6835, 3.5707, 4.1271, 4.6835, 3.5707, 4.1271, 4.6835),
  PCF = c(2.9550, 2.9550, 2.9550, 3.9209, 3.9209, 3.9209, 4.8868, 4.8868, 4.8868),
  SWL = c(3.6136, 4.0105, 4.4073, 3.8711, 4.2605, 4.6498, 4.1286, 4.5105, 4.8924)
)

# Crear los gráficos

gg_girls_8_12 <- ggplot(girls_8_12, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_point() +
  geom_line() +
  labs(title = "Girls 8-12 years old") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

gg_boys_8_12 <- ggplot(boys_8_12, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_point() +
  geom_line() +
  labs(title = "Boys 8-12 years old") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

gg_girls_13_18 <- ggplot(girls_13_18, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_point() +
  geom_line() +
  labs(title = "Girls 13-18 years old") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

gg_boys_13_18 <- ggplot(boys_13_18, aes(x = PL, y = SWL, color = factor(PCF))) +
  geom_point() +
  geom_line() +
  labs(title = "Boys 13-18 years old") +
  scale_color_viridis(discrete = TRUE) +  # Aplicar la paleta Viridis
  theme_minimal() +
  labs(color = "PCF")  # Cambiar el nombre del factor en la leyenda

# Unir los gráficos usando patchwork
combined_plot <- gg_girls_8_12 + gg_boys_8_12 + gg_girls_13_18 + gg_boys_13_18 + plot_layout(guides = 'collect')

# Mostrar el gráfico combinado
print(combined_plot)





#J-N EDAD



# Datos para las niñas de 8-12 años
girls_data <- data.frame(
  PCF = c(1.0000, 1.2105, 1.4211, 1.6316, 1.8421, 1.9306, 2.0526, 2.2632, 2.4737, 2.6842,
          2.8947, 3.1053, 3.3158, 3.5263, 3.6166, 3.7368, 3.9474, 4.1579, 4.3684, 4.5789, 4.7895, 5.0000),
  Effect = c(1.0465, 0.9937, 0.9409, 0.8881, 0.8353, 0.8131, 0.7825, 0.7296, 0.6768, 0.6240,
             0.5712, 0.5184, 0.4656, 0.4127, 0.3901, 0.3599, 0.3071, 0.2543, 0.2015, 0.1487, 0.0959, 0.0430),
  se = c(0.6000, 0.5560, 0.5126, 0.4697, 0.4277, 0.4103, 0.3868, 0.3473, 0.3099, 0.2753,
         0.2448, 0.2201, 0.2033, 0.1965, 0.1969, 0.2006, 0.2150, 0.2379, 0.2671, 0.3007, 0.3375, 0.3765)
)

# Datos para los niños de 8-12 años
boys_data <- data.frame(
  PCF = c(1.0000, 1.2105, 1.4211, 1.6316, 1.8421, 2.0526, 2.1077, 2.2632, 2.4737, 2.6842,
          2.8947, 3.1053, 3.3158, 3.5263, 3.7368, 3.8636, 3.9474, 4.1579, 4.3684, 4.5789, 4.7895, 5.0000),
  Effect = c(1.0031, 0.8938, 0.7845, 0.6753, 0.5660, 0.4567, 0.4281, 0.3475, 0.2382, 0.1289,
             0.0197, -0.0896, -0.1989, -0.3081, -0.4174, -0.4832, -0.5267, -0.6359, -0.7452, -0.8545, -0.9637, -1.0730),
  se = c(0.2938, 0.2757, 0.2589, 0.2436, 0.2303, 0.2192, 0.2166, 0.2106, 0.2049, 0.2024,
         0.2032, 0.2071, 0.2142, 0.2239, 0.2361, 0.2445, 0.2504, 0.2664, 0.2838, 0.3024, 0.3220, 0.3425)
)


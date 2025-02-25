#### Квоты {#mkf-quotas}

| Вид ограничения                                                              | Значение |
|------------------------------------------------------------------------------|----------|
| Количество кластеров в одном облаке                                          | 16       |
| Суммарное количество ядер процессора для всех хостов-брокеров в одном облаке | 96       |
| Суммарный объем виртуальной памяти для всех хостов-брокеров в одном облаке   | 640 ГБ   |
| Суммарный объем хранилищ для всех кластеров в одном облаке                   | 4096 ГБ  |


#### Лимиты {#mkf-limits}

| Вид ограничения | Минимальное значение | Максимальное значение |
|-----------------|----------------------|-----------------------|
| Класс хоста | b2.medium ([50%](../../compute/concepts/performance-levels.md) × 2 vCPU Intel Cascade Lake, 4 ГБ RAM) | m3-c80-m640 (80 vCPU Intel Ice Lake, 640 ГБ RAM) |
| Количество брокеров в кластере при использовании стандартного или быстрого сетевого хранилища | 1 | 7 |
| Количество брокеров в кластере при использовании нереплицируемого сетевого или быстрого локального хранилища | 3 | 7 |
| Объем данных на брокере при использовании быстрого сетевого хранилища | 10 ГБ | 4096 ГБ |
| Объем данных на брокере при использовании стандартного сетевого хранилища | 10 ГБ | 2048 ГБ |
| Объем данных на брокере при использовании нереплицируемого сетевого хранилища | 93 ГБ | 8184 ГБ |
| Объем данных на брокере при использовании локального хранилища | 100 ГБ | 1500 ГБ |

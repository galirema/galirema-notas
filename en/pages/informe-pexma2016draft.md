# Plan xeral 2016. Informe da planificación anual

## Tipos de planes

1. __Gráfico M01-01 Por tipo de plan__  

```sql
SELECT "anualidad", "tipoCode", COUNT("tipoCode") FROM "pexma2016" GROUP BY "tipoCode" ORDER BY "tipoCode";
```

![M01-01](https://lh3.googleusercontent.com/Y-YFRAEV4VJeMdSTDJWmz0tAtXd4Sa2NzDVqTdsxMQK2kxUTb0WopbKhmivg_GQy3SFSZek8pzw_ap9Yodwc8iX1SxgHOPlFe5kQlVBfIgSfr7xzvzfHwqUfA1Xm5BoE2ZGMksWWInpfwbZ_V3CMTeA6eJsCSOJtNCv5frDWL4KK0NDNBATbzorW3JKXYVr6HUGqsmzn8pN7e8cmy0q1akMf8M3NQ_Wd72F7sjqrmsTNyhU23jbvgykskp4i-LqSP-svDyQSEgeCNBro903yNJkIg26efu-5c8AA5wsXlJZrc9b_-Jt4sHSawt7ON3pytHkd8EGZDS7pXBFldNnir9IwuYt3SS4k0u95NyNj6aY1fLLEyAZQD93djJLWY72gTiHeCUXXeC1vmLpCu9e-o-x5oUW4d-fJ1NDj_c0JefrvTG2DwRCsa2jZXGv6S3CRTtxj9XWfarFWwqwycWJ27oOkKDVFtgDSalRueR-rSDAFAN0RMZh0N-XCjOW-OJ_boP3RvUu8K_MwJbMI4k2vmZaUnBpaB91pqfpxNl4RYIZe32-2FTDIqACZ42ej43wSzRZOsRe0NzS_d-zzMGGUmpu1WN82AYi1AqxuC1kkfIMmVhiK=w600-h450-no "M01-01. Plan General 2016. Tipos de plan")

* En el __Plan general de explotación marisquera para 2016__ determina las normas generales para las zonas de libre marisqueo (Art. 4) y crustáceos (Art. 6) y __205 planes anuales de explotación__ para zonas de producción concretas.

+ Los 205 planes se reparten en __8__ tipos de plan:
    + __Autorizaciones__ (AAUT, art. 2) 46 planes, 22,4%
    + __Especificos__ (BESP, art. 3) 48 planes, 23,4%
    + __Percebe__ (DPER, art. 5) 35 planes, 17,1%
    + __Equinodermos__ (FEQD, art. 7) 18 planes, 8,8%
    + __Solénidos__ (GSOL, art. 8) 25 planes, 12,2%
    + __Oreja de mar__ (HPEN, art. 9) 6 planes, 2,9%
    + __Algas__ (IALG, art. 10) 18 planes, 8,8%
    + __Anémonas__ (JANE, art. 11) 9 planes, 4,4%


* Entre los tipos de plan el marisqueo tradicional estaria representado por __AAUT__, __BESP__ y __DPER__ que suponen el 62,9% de los planes aprobados. Los restantes tipos de planes (37,1%), surgen después del Decreto 59/1992, bien porque su explotación no estaba legalizada o que los medios empleados para realizarla no estaban permitidos.


## Nivel de colaboración

1. __Gráfico M02-01-Nivel de colaboración. Plan General 2016__  
```sql
SELECT "anualidad", CASE WHEN UPPER("conxunto") != 'F' THEN 'Plan Conxunto' ELSE 'Individual' END, COUNT("conxunto") FROM "pexma2016" GROUP BY "conxunto";  
```

![M02-01](https://lh3.googleusercontent.com/MO8EPU_H_2sBD2yHxJqKvJ5Aj3N63UhmxQD0ND3-c2rODbuY60YSmwn14y3qI_HXWZzn7hHqSDYv4HGvEymmJO0hBUe27GXhCV56AWQ126L71DP2M7E8iNbLcPIbS1MjUZbAEs1Z5ht3GHIpBXIljebN9LqZqCT7ub-ziIJmZwhVT2fQrCyN8nX3aMmODPchmXSbFx_cMtWKFMtMs3T0rtQsahwhjOhnbYHa62-I44Kj_yV95y59QbvGAzt3GKHvcvGVtWQdzIpjDqtxF1JY2n9RFw9bkoenECd4izfc41W0_gQIGsgjskdbSUk-e3AoEDUVVQdARmi8Bhl_aIG-oQBqF5ioRHH61jx5juQI7qnJD32L4YBJFyD_oYJKv0T1pyJwAutkEs5r8d8hj0hGpdhGUkITw65AF0zXn98djHY05B_wGBDpiysbEHZYx6sSHNq70U59BRuIwdQTXwBwosLnLamk5tSlQLRoY0EdzoLEmROiXFbw1fYZoT-H6ud4mtOD1CxlrCI2eESkZGXoiy02RECrTFUGS0-2k-s9JNcZWYK4eT_JoLtM45oDdBkcPin7sm9Dfk378cBoXlwsR9-1mTBP6AU__wWURFB98ubO5z1K=w600-h450-no "M02-01. Plan General 2016. Nivel de colaboración.")

* La presentación de planes conjuntos entre varias entidades aporta la...

1. __Gráfico M02-03 - Nivel de colaboración por tipos de plan 2016__  

```sql
SELECT "anualidad", "tipoCode", CASE WHEN UPPER("conxunto") != 'F' THEN 'Plan Conxunto' ELSE 'Individual' END, COUNT("conxunto") FROM "pexma2016" GROUP BY "tipoCode", "conxunto" ORDER BY "tipoCode";  
```

![M02-03](https://lh3.googleusercontent.com/6-29PUWfcKQD5H6xDaqz3f4WjV-JO3LLgdVf9sls7YlXJnrvbA9sWPjjKGcGJGrU_4E5Iq-IaZVqJhm7aRnEfZnkQfzapL0S9IC3R74o6tkclvzXj3puEM7k0DEPJK7tKTPheMLDDFASaGoNy1ZNg2UA3FqknyC8_ZU6FKGaCMCIUtEy0h5Pm6ZSndv6fvBVto4B7mUGXaHAcNspvGE0MG98U9xrm3zgYnt3C9gEo9HeToeVBw5Lv-UVJOhUIE7rbCe-SMEw8m3KJhwR98d7p4pAz8ssMoLFJ1_nfhKTkhatcHhzO0VlafzTwaAtjLlcflqRckJbhVk-TVd3jGqrB-V1mScm8eBtf8ke2KyOc4Sb9ko1sdof5npWsG8EjbQfMWVFVA3oNtICTafZPIWVNT4_9W9dOXvgxPLHUaY1fAzXJdQCf2SAe3AxF8tV1GklHs-9a_-y1t_cSYQPFPElxrVMp7qKjD86AvI9xtQKT4NrF_IPwpdyxiMZs4WVVSq11itXE-Z-SV9ZAcM2CSWLp_BM4W7TmE7QX-7A6uEURM6RmOJB_S7oOJcFHw620i284UQ17-x9HSC01IvFhjHtJWwgbwR1SGHM-fiXPFh4SOPmGjaF=w864-h728-no "M02-03. Plan general 2016. Nivel de colaboración por tipos de plan")

* No todos los tipos de plan presentan el mismo nivel de colaboración siendo estos mas elevados en los tipos de plan que se generarón con la legislación actual. En los planes que representan la explotación tradicional del marisqueo tienen un bajo nivel de colaboración menos en los planes especificos para zonas de libre marisqueo (Art. 3, BESP) al actuar sobre zonas donde tradicionalmente trabajan mariscadores procedentes de varias cofradias.


## Especies aprovechadas

1. __Gráfico M03-01 Especies aprovechadas__

```sql
-- Moluscos
SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'A%' OR "tipoCode" LIKE 'B%' OR "tipoCode" LIKE 'G%' OR "tipoCode" LIKE 'H%' GROUP BY "codeFAO" ORDER BY "codeFAO"; 
  
-- Crustáceos 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'D%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Equinodermos 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'F%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Actinias 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'J%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Algas 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";

```

![M03-01](https://lh3.googleusercontent.com/SbJgFLD0_175HBMZZU6yDlqaaI4zYBa1AcrqQrduiNt8rOZaPNiqn15eySQ9cG1xbaJ7jMnqGtCBzrkhl2khBnU1y5HaqWnAPX3a0ND2KRn6vTadCXaLHhT3TiYlMS8sBt2SO9BVoTRuY5QJ9LJKYW9bEXp8YQp3ozNZ-K9Srn0W9litchYFvn5ux0h8n2UwgjQ2MqUh-wY1F7QcUPwjLZpFQy6quux1mJwN7iQ_apMHm-NATbkwFy-MJcfWTEXgSFXSL1Tzq8-bnDznhNC15h0f4lJhifcyAHglOafAGFzIJXcYEjL5uq84187cVDANTvCLf4Qu01R04VkhmAeqRBkOUufXQV-DmFIBadbSOIoXRwpCtJtuhqYCwfiRD2oG6t4Uk_B7eMfOnchJmy5VDCBkj_xWP45VITNpAiKx-J-cdp2HRN-hwrhFYR5W_Beuutm3OCFVcMh1UbpcZ0u88zOcfTMNcxeyVWN3M5HhMGj08gs905011bJA03YHYRrN750MTLjUqLjjkst5G69S2i-OH-Y1x4P6rvJyGRjrq3ljyZh7IvDhPf9lJgPO4Mmc0caemg7PEVWD0sXJ1r5ri98wsEi-W--CSqsw1Sl6uwIX_s0y=w600-h450-no "M03-01. Plan general 2016. Especies aprovechadas")


## Modalidad de captura

1. __Gráfico M04-00x. Planes por modalidad de captura. __  

```sql
SELECT "codeMod", COUNT("tipoCode") FROM "pexma2016" GROUP BY "codeMod" ORDER BY "codeMod";
```

![M04-00x](https://lh3.googleusercontent.com/NcLFOgfAClCGLcCwqizdhLraZR1KuL39d7oxaICgczebZa0lltBuLgLUc-2HVIV6zIFojFvDboM8pPMUkEoiDqogRvZve8XwrxrwuctKwZ0WZhwlrRz6xWFaEYVfWbGyB8KW2g6um1Tqg4ya4ETdq2llfjkfg_z7RWp_rcrq2yjfuOLoL_Fvdqf4BswSg6ZD2M9bhSdVi1NN37Rsl5gqiA0G_orJyxBqu3tCRR2P_luxcKOL6upRdjypxlpPQWLARX5sYuKIDnqFN7IQkSiGoXGlUSqGBgXlnQcPYlx_Hg-77zI88zyGjmCC4fgk_LRLxP80x3vqemsR4Rk8j7cZx_ycXDxV5SMrocIGoLN8Rtn0zB0KmFUkrlbIMVWqF3Wo7LUSygq6GlKfF8C5SuPwNTDGMlR-5GjnH6yzQlvlzHhFNpYDyWBOoOVFZbpl3piB-5mMvKh1Puobx_SF0TgBgGRxvaZ6oz5Uu9U0-z0IBm02EbtxOy99f7dDRvbkfXjnh51cOPs0YXFSMoz7TjVCudUigULqRjvF47IEXoKDKHIjwJBTintsiXdZfSzFDQnIK7SL4h1ie5npDE8_loQA9r7YkzqV-V2k-xH0stLCSL4bFvF7=w600-h450-no "M04-00x. Plan General 2016. Planes por modalidad de captura.")

1. __Gráfico M04-01 Modalidad de captura por tipo de plan__  
```sql
SELECT "tipoCode", "codeMod",  COUNT("tipoCode") FROM "pexma2016" GROUP BY "codeMod", "tipoCode" ORDER BY "tipoCode", "codeMod";
```
![M04-01](https://lh3.googleusercontent.com/kRIToN6oufnIqTN_-1gqyxZe7Z1mFJDHfQ-KnUlgiUubxhEKvooZRjFDR9j7rO6R-W86nyb0-84zY-voowqPWVIRBTVk7DJpkppiz8IQ0gNVwwLYGEBa0LHF8u9i562N5Hg2eXhiGWqEn1-xubOE512x_X8Y4zALlC9RzZLW33oXDNY04JQ0lcyA3opzk6f9phVCPRg297YwJqBSZxwCUuaBdzXYNIATC3fyepG0cvQrHkZM7xjXHWVMFIno5iINxsULTCRREe4Dk5ABgOq77Qv_zpn0q1MFishk7sCCjLpF30jn-NKP0RjWV2-PjT0c5otNrhjjlGekVjEu0Pm3NqHTjwkIHZTsjvZEjJ5hypugTWEi4siG4QP4sVPNBrXZZyWaS2Koigbol5cVug_eErg9McYERlVNbhxSf247xN1n6bjJOrOnDYuMbPqMjQlqKxXapyeHz2vjuZa7l0XCxgTZQFSEmxH35K18wbK5E-Iuf_j-hpAZZkrTUEkNFxmLvgZj7ef5m8Ftco6Ok8pBRD3fdvw3CcUh7Ic9hqU7JJUuCr0NZFXJSxQLs6fQTHUFkbgLrHCmO8T5kBIG7J8GR3B9Pm4x38LnV6AeqyAvp1GN5I4y=w850-h500-no "M04-01. Plan General 2016. Modalidad de captura por tipo de plan")


## Entidades Promotoras

1. __Gráfico M06-01 Tipo de entidades promotoras de planes de explotación en 2016__  
    * Basado en la vista __entidad16-01__  

```sql
CREATE VIEW "entidad16-01" AS  SELECT "pen16.ideplentidad", "pen16.anualidad", "pen16.idPlanAnual", "pen16.entidad", "cfd.tipoentidad", "cfd.activa", "cfd.id_cofradia", "cfd.costa" FROM "plantidad2016" 'pen16' INNER JOIN "cofradias" 'cfd' ON "pen16.id_cofradia" = "cfd.id_cofradia" GROUP BY "cfd.id_cofradia" ORDER BY "cfd.tipoentidad";
 
SELECT "tipoentidad", COUNT("tipoentidad") FROM "entidad16-01"  GROUP BY "tipoentidad";
```

![M06-01](https://lh3.googleusercontent.com/M-D1vmK7weGKcHk0sESAV1N-4W8X_eIPowpYEf3O_WUStRVusWQXT1TecinuPGDBhQPMn8xDDiHk87GNxopcOu3B4ntMkW_AtqMvDb8G-gk7NYbAhro5EyBMiqP4MfK_vStLOwxgNeimAxLCdloQ8Mx60NYmdUwdQttynp-Mc9tTFaNBfKmfOcHJSQo_VVltebygVf_ptrPCxYGbcVgToHXdNGze0jnhCztXnZJnjeTpWLt2F9UsvYwjbsZYjiKQBNq7oQa-aKSA7sEZafyY_VKbiQcb_Om9rKJKQmzJTHWbE57lDQwppath1niyOlHk9zLvDnXA-DkX9YVzBUNyT_sL5sEncp55pYKLZznUorOIOfjfGl_Fo8IrxGjrhQ3mIMWEeqUG728GJBaNqlGIUixLT2effWlrhn-lRo_jNuVGV7L4_CXSdE3z4StmYnVJtgzUzzy5qawlI_nQQhH0DOPX2ByEU5Iuz-8I8GhZj5j9jNvuyl_5CBlM8FaUc7Hzm4YLTTuQmlP9_UJEr6oiwkBrbzz-IdVoAHe24oc4cOvtkSYNe4oaLfsPESm-eWZka1WyB8qydl98Fpa7SBpO7tS-Els61iIcG-qnHcmDjv0bbLsE=w600-h450-no "M06-01 Tipo de entidades promotoras de planes de explotación en 2016")


1. __Gráfico M06-02 Entidades por tipo de plan. Plan general 2016.__  

```sql
CREATE VIEW "entidad16-02" AS SELECT "pen16.ideplentidad", "pen16.anualidad", "pen16.idPlanAnual", "pen16.tipoCode", "pen16.entidad", "cfd.tipoentidad", "cfd.activa", "cfd.id_cofradia", "cfd.costa" FROM "plantidad2016" 'pen16' INNER JOIN "cofradias" 'cfd' ON "pen16.id_cofradia" = "cfd.id_cofradia" ORDER BY "pen16.tipoCode", "pen16.idPlanAnual";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'A%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'B%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'D%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'F%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'G%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'H%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'I%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'J%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" GROUP BY "tipoCode", "tipoentidad", "entidad" ORDER BY "entidad";
```
![M06-02](https://lh3.googleusercontent.com/i36GfELvk_tL8KpsvpNMXiH7ljr7F786BFeNMyRrD66dRcpm4X_C95bZaTvm_yAhEagWkhZf5MXy1ceRYWIQy44revMI0BUEDTsvolO1lxPj_i3fxqrGK_85-KnAXRhrTx5Vxu0Dz_KgyzfR3Cxp6apIQI8j9ZB20EXrfTugiui9KaVBZP94wjFI3dtfmSEbtuo3YIEXrDGtjgOARERahsfZkdEzKUUSmzg_w6q2r2qaaubsDsS0REojuKJa87OiAZEpA-zx2WQnNr3o82avYC0UpHqdR-1QyJHrEl46V698OOi4Y2XByrpnyL27ucMbEXu4ImHpQkq-kIs6kCUfKw5oFhyX9_HY929gdEFPj_gFOSjjkD2sjWzVxNcjhLZAQT1yW6DT2WowEu8-JC9KGHE06UIIKS1iIB1zUMbn9s_-1MUSF01BGznwpqv_Pg2SPHeY55lBXLzUqVphe6WeXXuFPbPSIatnWmxQC8EkIKa1gRH1I0WVPpIudtKtnKn4wwnRbQDf1sDD8hSZlNkveoQ4VQdYKTB76RNCQdoUbv8LcYZUxfmIp1v5s8Ts_3mCJPV-8LAdRpGIESMEs6fciBj7i2FClHFL09uTk_dDql_IU8nm=w922-h777-no "M06-02. Plan general 2016. Entidades por tipo de plan.")

1. __Gráfico M06-03: Número de planes por entidad. Plan general 2016.__  

```sql
SELECT "anualidad", "id_cofradia", "entidad", COUNT("id_cofradia") AS 'Num. Plans' FROM "plantidad2016" GROUP BY "id_cofradia" ORDER BY "Num. Plans" DESC;`  
```
![M06-03](https://lh3.googleusercontent.com/_gNtHRkB9rnU3dXqvdVEZJGuoVa4gL9GIe0PrM_NYDyegabkXHGzgdIjFaaYJZ29llTHwhr5lpSA0R4wGrj8niizkkEWG3uSwkLZgZLC4EF8_9gUk6wDIhtmquHirjj_Y7XEKPw6p9kKn0HDaZK9Ov94BoGgOpt0Uzie9Fq4uUjSJDyomB_xA0Qyk8fRcNxrkdds2wFsSTxn1OMXTtBtFSmTUPUi-bT_OyAFRAxGjxFyH4B4FeEvz1RQIt-3qATFphxZnIkUht6bQrLHKPDHsZCV0qyW2QG4mTW695zloMxLkkvda0QdXxba6XYIOsklMNssuZRW0zvGWfyN5_tfOGyDjEONBwqjc072kcIXGJgdWG2ayvmH8nPT8g_latuCnMGSMJoy70-5UIjGkmEFl2hh6zaOKr0YwDq5Lsn8J80p_k8bmkhLKV0kkGo9EqNXB9JhCwjlQ7CD5fMSVfaWVfjfhg_nFSJLR3rD09tMh_ocILiwB2w_04cL-kWxZqyZH04B7DQsPdHs2gmBJp1Gw_cIF7F3Hwdeo8YpqwQ0cgSPD_bcGNeAyyq75AgJAWDZ8pFNFad80kbNOV2LOki3lH38g3_d0yPijwyp_2rtXOPU_mV-=w650-h450-no "M06-03: Plan general 2016. Número de planes por entidad.")
 

## Distribución por zonas de costa

1. __Gráfico M07-04 Entidades y planes por zona de costa__  

```sql
SELECT "costa", COUNT("id_cofradia") FROM "entidad16-01" GROUP BY "costa";

SELECT "costa", COUNT("idPlanAnual") FROM "pexma2016" GROUP BY "costa";  
```
![M06-04](https://lh3.googleusercontent.com/zvYVJOZhEAQvSIS266pzKpGZ8weCeHbBR494ikqoHaOBTzXJAGlWs2pUl8tXLUdQSrF-hbi-VIYKfOw0PdmOy6fAwLAQI3WQgSIOTsVBuvwErirv5MQFwowsJl0l-6JbGG2FWpH-y8KHeT-vzZFgfEzwObbVDQ7L7YXenIaYKfX2Yq423VXfYJdn8RKgKgxQ8sufw0v2Ks2oSy1tUMqYJkD3MpoS2lXGN1cqekjdzovW5eXcO7glnxFAIh47WrKO0u76pgkl_ZWGlSP8XRbs1_khZPDeZrxFX0iS9d4POovuSiNZsDAU08BpZ-lxcys2LfiLsaHTq5ffJN0jflIhujyMDhcogqdrG4tVwXoWFW42ZeoYUKpPPZGkf5u88ZZDmk3sj8508_lil_clRZZlh7bLaDrqEwQ8pTVONUlku1Wycy_DEq2iWr6gI1fCfxV_gBlIVI2yPYQTRd2qDwIiILtmE6M20vZOfVzTUC7Y00d3QFSLEWG5cNWRhvzJDmlawdZ699iQEM5WumaspTgxuaaEVgCOHxckpd1uNNhbG1dPzAF5iSgo0T9IWjWGr_-S6THQgfyOwGpyE9fNJAg4lKxgtOG63mWYl1Mj3OH0zN3ZQdHJ=w750-h450-no "M07-04: Plan General 2016. Entidades y planes por zona de costa")


1. __Gráfico M06-05 Tipo de plan por zona de costa__  

```sql
SELECT "costa", "tipoCode", COUNT("idPlanAnual") FROM "pexma2016" GROUP BY "costa", "tipoCode";
```
![M06-05](https://lh3.googleusercontent.com/SZSflDZCDy4Hvx1khf57IgYhLw34Ug77drD-DA7lKNWUIFXuWx7V0CQZ8avKGwOAaBgY5WnL5aXS9wjNTB3QgERNCcHQNsCe7OcETBYUodSYsBhFjMAhLO5SZ8sGayBhJa6p5_tEflc72171J2bpmJbytaU_88HxeL_i78zlMYuPqXr8HYZFwKv_-JlxWY4-zTzlMdYLSM1o3JzIzVlU3YmwjqChWCj6-C8F5G1KIDnNPtLwc0JskBZCBmBmBAyZ_K9UlCptezW7S988O4-pcu1B--pGL4efytWCQTdhdSsgo7vDBkumxJMy27zlB8q8eGvkR31gsbJA_F4DBxzXu830jPJkXOt8XYfpTDVQv9z14X6YlVQCTcKk6MDF-piDqpXdtIlpB9n_m-8YpPY__ny_6IlCh2grvl9hpc5vqMupyPJORDeRo3v-B3xptSxrR8UvboYoZlamY1L3pwDewO8qAlB_UkZGdF1M6Hhnm1rPtc6r7GeJN_BT7p5wAFRUF9mw5iKIZb5BcjYaU92YUOb_vlRaRfY3dPcwcM82mwTnS6AckHGC2rEUcEj9SXcny8D3k3pX56BdP4Iuyt1rIS_Th7reltRKQtR3AgcDB2jjRuwK=w850-h500-no "M06-05: Plan General 2016. Tipo de plan por zona de costa.")

-----

## Datos de los gráficos

+ M01-01

|año|Tipo de plan|num. de planes|
|:--|:----------:|-------------:|
|2016|AAUT|46|
|2016|BESP|48|
|2016|DPER|35|
|2016|FEQD|18|
|2016|GSOL|25|
|2016|HPEN|6|
|2016|IALG|18|
|2016|JANE|9|


* M02-01

|Plan|Num. de planes|
|----|-------------:|
|Individual|172|
|Plan Conxunto|33|


* M02-03A

|Tipo de Plan|Individual|Plan Conxunto|% individual|
|:----------:|---------:|------------:|-----------:|
|AAUT|45|1|97.83|
|BESP|37|11|77.08|
|DPER|34|1|97.14|
|FEQD|12|6|66.67|
|GSOL|16|9|64.00|
|HPEN|4|2|66.67|
|IALG|16|2|88.89|
|JANE|8|1|88,89|


+ M03-01

|Grupo|Num. Especies| % |
|-----|------------:|--:|
|Moluscos|27|40,91|
|Crustáceos|1|1,52|
|Equinodermos|2|3,03|
|Actinias|1|1,52|
|Algas|35|53,03|


+ M04-00x

|Modalidad|Num. de planes|
|:-------:|-------------:|
|A|75|
|B|39|
|C|23|
|D|5|
|E|2|
|F|15|
|G|5|
|H|36|
|I|1|
|J|2|
|K|2|


+ M04-01

|Tipo de plan| A | B | C | D | E | F | G | H | I | J | K |
| :--------- | --| --| --| --| --| --| --| --| --| --| --|
| AAUT       | 24| 14|  6|  2|  0|  0|  0|  0|  0|  0|  0|
| BESP       | 28| 12|  3|  3|  2|  0|  0|  0|  0|  0|  0|
| DPER       |  8| 13| 14|  0|  0|  0|  0|  0|  0|  0|  0|
| FEQD       |  5|  0|  0|  0|  0|  8|  0|  3|  1|  1|  0|
| GSOL       |  1|  0|  0|  0|  0|  0|  5| 19|  0|  0|  0|
| HPEN       |  0|  0|  0|  0|  0|  1|  0|  5|  0|  0|  0|
| IALG       |  8|  0|  0|  0|  0|  3|  0|  5|  0|  1|  1|
| JANE       |  1|  0|  0|  0|  0|  3|  0|  4|  0|  0|  1|


+ M06-01

|Tipo de entidad|Num. Entidades|
|:--------------|-------------:|
|CFP|61|
|AGM|4|
|COP|2|
|EMP|5|
|ASC|1|


* M06-02 2016

|Tipo de plan|Cofradías|Asoc. de Mariscadores|S. Coop. Galega|Empresas|Asoc. Cofradías|
|:-----------|--------:|--------------------:|--------------:|-------:|--------------:|
|AAUT|28|2|1|0|0|
|BESP|42|3|0|0|1|
|DPER|36|1|0|0|0|
|FEQD|29|2|0|0|0|
|GSOL|34|0|1|0|0|
|HPEN|14|0|0|0|0|
|IALG|19|0|0|5|0|
|JANE|10|0|0|0|0|



* M06-03

|Num. planes|Num. Entidades|{ role: 'style' }|{ role: 'annotation' } |
|:----------|-------------:|-----------------|:---------------------:|
|1|11|#B464FF|11|
|2|15|#B464FF|15|
|3|14|#B464FF|14|
|4|9|#B464FF|9|
|5|8|#B464FF|8|
|6|4|#B464FF|4|
|7|5|#B464FF|5|
|8|6|#B464FF|6|
|9|0|#B464FF|0|
|10|1|#B464FF|1|
|11|0|#B464FF|0|
|12|0|#B464FF|0|


* M07-04

|Zona de Costa|Planes|Entidades|
|:------------|:----:|:-------:|
|Galicia (GL)|5|5|
|Costa Lucensa (CL)|25|11|
|Coruña-Ferrol (CF)|27|12|
|Costa da morte (CM)|27|10|
|Muros-Noia (MN)|11|4|
|Arousa (AR)|52|13|
|Pontevedra (PO)|17|8|
|Vigo (VI)|41|10|


+ M07-05 Tipo de plan por zona de costa 2016

2016

|Zona de costa|AAUT|BESP|DPER|FEQD|GSOL|HPEN|IALG|JANE|
|:-----------:|---:|---:|---:|---:|---:|---:|---:|---:|
|CL| 3| 8| 9| 4| 0| 0| 1| 0|
|CF| 11| 7| 4| 2| 0| 0| 1| 2|
|CM| 2| 5| 10| 3| 4| 1| 2 |0|
|MN| 4| 1| 2| 0| 3| 0| 1| 0|
|AR| 23| 9| 3| 2| 10| 2| 1| 2|
|PO| 1| 5| 2| 2| 2| 2| 2| 1|
|VI| 2| 13| 5| 5| 6| 1| 5| 4|
|GL| 0| 0| 0| 0| 0| 0| 5| 0|







# elecciones2017
Repositorio con datos de las elecciones 2017

Archivos:

```PASO/provisorio/PR_ARGENTINA2017.mdb``` Base de datos original, obtenida del programa 
publicado en www.elecciones.gob.ar, el 18/08/17
```PASO/provisorio/PR_ARGENTINA2017.mdb.sqlite``` Misma base de datos, en formato sqlite (para los que no tienen access)


Datos interesantes
------------------

Si se tira la siguiente query:

```
SELECT n.parDenominacion, sum(m.votVotosPartido)  as Votos
FROM MesasCandidaturaSNacionales m, nomPartidos n
WHERE m.vot_proCodigoProvincia = '02' AND
     n.parCodigo = m.vot_parCodigo
GROUP BY m.vot_parCodigo, n.parDenominacion
ORDER BY Votos DESC
```

El resultado es:

```
"UNIDAD CIUDADANA                                    "	"3095177"
"CAMBIEMOS BUENOS AIRES                              "	"3089071"
"1PAIS                                               "	"1405529"
"FRENTE JUSTICIALISTA                                "	"534668"
"FRENTE DE IZQUIERDA Y DE LOS TRABAJADORES           "	"306655"
"IZQUIERDA AL FRENTE POR EL SOCIALISMO               "	"95837"
"CREO                                                "	"48888"
"FRENTE SOCIALISTA Y POPULAR                         "	"48156"
"FRENTE PATRIOTA BANDERA VECINAL                     "	"32811"
"FEDERAL                                             "	"30714"
"HUMANISTA                                           "	"23999"
"TODOS POR BUENOS AIRES                              "	"17306"
"DEL CAMPO POPULAR                                   "	"9402"
"MOVIMIENTO ORGANIZACION DEMOCRATICA                 "	"7481"
"MOVIMIENTO AMPLIO DE TRABAJADORES Y JUBILADOS       "	"1785"
```

Idea obtenida de: https://www.facebook.com/marzullo/posts/10212862291088791?pnref=story
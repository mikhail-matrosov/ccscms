# CCSC-MS
Combined Clinical Score Calculator for Multiple Sclerosis

Калькулятор Объединенного клинического показателя рассеянного склероза

<html>
<head>
	<title>Объединенный клинический показатель РС</title>
</head>
<body>

<h1>Калькулятор Объединенного клинического показателя рассеянного склероза</h1>

<div style="font-size: 24">

<input id="age" type="number" value="40" style="font-size: 24; width: 100;"/> Возраст, лет<br>
<input id="ft" type="number" value="8" style="font-size: 24; width: 100;"/> 25 FT, сек<br>
<input id="fptd" type="number" value="22" style="font-size: 24; width: 100;"/> 9 HPT D, сек<br>
<input id="fptnd" type="number" value="26" style="font-size: 24; width: 100;"/> 9 HPT ND, сек<br>
<input id="sdmt" type="number" value="49" style="font-size: 24; width: 100;"/> SDMT, правильных ответов<br>
<br>
ОКП РС: <b id="result" style="font-size: 36">0</b>
</div>

<script type="text/javascript">
function calc(event) {
	result.innerHTML = Math.round(
		(
			+0.082 * Number(age.value)
			+0.168 * Number(ft.value)
			+0.153 * Number(fptd.value)
			+0.102 * Number(fptnd.value)
			-0.075 * Number(sdmt.value)
			-7.328
		) * 100
	) / 100
}

age.addEventListener("input", calc)
ft.addEventListener("input", calc)
fptd.addEventListener("input", calc)
fptnd.addEventListener("input", calc)
sdmt.addEventListener("input", calc)
calc()
</script>
</body>
</html>
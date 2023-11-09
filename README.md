kotlin
Thread {
    val app = application as App
    val dao = app.db.calculoDao()

    if (calculoTipo == "tmb") {
        dao.inserir(Calculo(tipo = "tmb", resultado = tmb))

        runOnUiThread {
            Toast.makeText(this, "Medição TMB salva com sucesso!", Toast.LENGTH_LONG).show()
        }
    } else if (calculoTipo == "imc") {
        // Substitua 'imc' e 'imcResultado' com as variáveis apropriadas para o IMC
        val imc = 25.0 // Substitua pelo cálculo real do IMC
        dao.inserir(Calculo(tipo = "imc", resultado = imc))

        runOnUiThread {
            Toast.makeText(this, "Medição IMC salva com sucesso!", Toast.LENGTH_LONG).show()
        }
    }
}.start()

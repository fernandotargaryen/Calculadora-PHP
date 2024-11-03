# Calculadora-PHP
Calculadora bacana, feita por PHP com código super simples! 

Antes é necessário instalar a última versão do PHP.  
Abri o Prompt de comando ser estiver usando o Windows e digite
Primeiro: mkdir php-server
Segundo: php-server
Terceiro: php-server>code .

Vai entrar automaticamente no seu VScode (Tem que está instalado em sua maquina)

Após add o código por completo, entre no terminal do VS e digite:
php -S localhost:8000 -t public (Esse public foi a pasta que criei para adicionar no VS e manipular os arquivos php e css, sendo assim voce pode renomear o que quiser na pasta)

A pasta para desenolver dentro do VS code, onde lá foram dois arquivos.
1 index.php 
2 style.css

Index.php:
<?php
$resultado = '';
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $numero1 = $_POST['numero1'];
    $numero2 = $_POST['numero2'];
    $operacao = $_POST['operacao'];

    switch ($operacao) {
        case 'soma':
            $resultado = $numero1 + $numero2;
            break;
            case 'subtracao':
                $resultado = $numero1 - $numero2;
                break;
                case 'multiplicacao':
                    $resultado = $numero1 * $numero2;
                    break;
                    case 'divisao':
                        if ($numero2 != 0) {
                            $resultado =$numero1 / $numero2;
                        } else {
                            $resultado = 'Erro: Divisão por zero!';
    }
    break; 
    default:
    $resultado = 'operacão inválida.';
}
}
?>
<!DOCTYPE HTML>
<HTML LANG="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Calculadora PHP</title>
        <link rel="stylesheet" href="style.css">

</head>
<body>
    <div class="titulo">
        <h2>Calculadora Bacana 😀</h2>
</div>
<form method="post">
    <input type="number" name="numero1" placeholder="Número 1" required>
    <input type="number" name="numero2" placeholder="Número 2" required>
    <select name="operacao" required>
        <option value="soma">Soma</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
</select>
<button type="submit">Calcular</button>
</form>
<div class="resultado">
    <?php
    if ($resultado !==''){
        echo "Resultado: $resultado";
    }
    ?>
    </div>
</body>
</html>





Style.css:
html, body {
    height: 100%;
    width: 100%;
    margin: 0;
    padding: 0;
    background-color: rgb(22, 22, 75);
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
}
.titulo, .resultado {
    width: 100%;
    max-width: 600px;
    margin: 10px 0;
}
form {
    display: flex;
    flex-direction: column;
}
input, select, button {
    margin: 5px 0;
    padding: 10px;
    width: 100%;
    max-width: 200px;
}
.resultado {
    background-color: rgba(255, 255, 0, 0.5);
    padding: 20px;
    border-radius: 10px;
}

Depois é só divertir usando a calculora :)
Voce também pode mudar os esilos e combinações da pagina. 



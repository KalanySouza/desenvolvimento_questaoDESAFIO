# desenvolvimento_questaoDESAFIO
questão desafio 4 do livro  - desenvolvimento web

<?php session_start(); ?>

<html>
<head>
    <title>Lista de contatos</title>
</head>
<body>
    <h1>Lista de contatos</h1>
        <form>
            <fieldset>
                <legend>Cadastrar contato</legend>
                <label>
                    Nome:
                    <input type="text" name="nome" />
                </label>

                <label>
                    Telefone:
                    <input type="tel" name="tel" />
                </label>

                <label>
                    Email:
                    <input type="email" name="email" />
                </label>

                <br><br><br>

                <label>
                    Descrição:
                    <input type="text" name="descricao" style="width: 500px; lenght: 500px;">
                </label>

                <input type="submit" value="Cadastrar" />

            </fieldset>
        </form>
        <?php
if (isset($_GET['nome'])) {
$_SESSION['lista_contatos'][] = $_GET['nome'];
}

if (isset($_GET['tel'])) {
    $_SESSION['lista_contatos'][] = $_GET['tel'];
}

if (isset($_GET['email'])) {
    $_SESSION['lista_contatos'][] = $_GET['email'];
}

$lista_contatos = array();
if (isset($_SESSION['lista_contatos'])) {
$lista_contatos = $_SESSION['lista_contatos'];
}
?>

<table>
<tr>
<th>Lista</th>
</tr>
<?php foreach ($lista_contatos as $contatos) : ?>
<tr>
<td><?php echo $contatos; ?> </td>
</tr>
<?php endforeach; ?>
</table>

</body>
</html>

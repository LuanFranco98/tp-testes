# tp-testes


**Nome:** Luan Silveira Franco

**Matrícula:** 2017068777

**Projeto:**   Link: https://github.com/joke2k/faker

Faker é um pacote Python que gera dados falsos para você. Se você precisa inicializar seu banco de dados, criar documentos XML bonitos, preencher sua persistência para fazer um teste de resistência ou anonimizar dados obtidos de um serviço de produção, o Faker é para você.


**Teste 1**
```python
def test_unspecified_locale(self):
    fake = Faker()
    assert len(fake.locales) == 1
    assert len(fake.factories) == 1
    assert fake.locales[0] == DEFAULT_LOCALE
```

O teste 1,***test_unspecified_locale***, testa se, ao criarmos a classe **Faker** sem passarmos nenhum parâmetro, obtemos uma classe com uma única fábrica, e um único *locale*, que deve ser também o *DEFAULT_LOCALE* definido em config.py.

**Teste 2**
```python
def test_add_dicts(self):
    t1 = {"a": 1, "b": 2}
    t2 = {"b": 1, "c": 3}
    t3 = {"d": 4}

    result = add_dicts(t1, t2, t3)
    assert result == {"a": 1, "c": 3, "b": 3, "d": 4}
```


O teste 2,***test_add_dicts***, que faz parte dos testes dos métodos "úteis" testa o método responsável pela adição de dois ou mais dicionários, tal adição ocorre de forma que as chaves comuns terão seus valores adicionados.

Para testar tal método, são criados 3 dicionários cujas chaves são Strings e os valores Inteiros, sendo que o dicionário t1 e o dicionário t2 possuem a chave "b" em comum.Ao somar os dois dicionários é conferido se o dicionário resultante da soma é equivalente a um dicionário com todas as chaves únicas dos 3 dicionários e se a chave comum dos dicionários t1 e t2 possui valor equivalente a soma dos valores da chave nos dois dicionários.

**Teste 3**
```python
def test_locale_as_string(self):
    locale = "en_US"
    fake = Faker(locale)
    assert len(fake.locales) == 1
    assert len(fake.factories) == 1
    assert fake.locales[0] == locale
```

O teste 3,***test_locale_as_string***, testa se, ao criarmos a classe **Faker** passando como parâmetro apenas uma String, obtemos uma classe com uma única fábrica, e um único *locale*, que deve ser igual à String que foi passada como parâmetro.



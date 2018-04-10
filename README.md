
<script src="http://code.jquery.com/jquery-1.10.2.min.js"></script>
<script>
    $(function () {
        $.getJSON('https://api.mercadolibre.com/sites/MLB/categories', function (categories) {
            for (var i in categories) {
                $('#categories').append('<option value="' + categories[i].id + '">' + categories[i].name + '</option>');
            }
        });
    });

    function getSubCategories1(id) {
        $('#subCategories1 option').remove();
        $('#subCategories2 option').remove();
        $('#subCategories3 option').remove();
        $('#subCategories').append('<option id="loading">Carregando...</option>');
        $.getJSON('https://api.mercadolibre.com/categories/' + id, function (data) {
            subCategories = data.children_categories;
            for (var i in subCategories) {
                $('#subCategories1').append('<option value="' + subCategories[i].id + '">' + subCategories[i].name + '</option>');
            }
            $('#subCategories1 #loading').remove();
        });
    }

    function getSubCategories2(id) {
        $('#subCategories2 option').remove();
        $('#subCategories3 option').remove();
        $('#subCategories2').append('<option id="loading">Carregando...</option>');
        $.getJSON('https://api.mercadolibre.com/categories/' + id, function (data) {
            subCategories = data.children_categories;
            for (var i in subCategories) {
                $('#subCategories2').append('<option value="' + subCategories[i].id + '">' + subCategories[i].name + '</option>');
            }
            $('#subCategories2 #loading').remove();
        });
    }

    function getSubCategories3(id) {
        $('#subCategories3 option').remove();
        $('#subCategories3').append('<option id="loading">Carregando...</option>');
        $.getJSON('https://api.mercadolibre.com/categories/' + id, function (data) {
            subCategories = data.children_categories;
            for (var i in subCategories) {
                $('#subCategories3').append('<option value="' + subCategories[i].id + '">' + subCategories[i].name + '</option>');
            }
            $('#subCategories3 #loading').remove();
        });
    }
</script>

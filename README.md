function verificarBandeira(numeroCartao) {
    const bandeiras = {
        'Visa': /^4[0-9]{12}(?:[0-9]{3})?$/,
        'MasterCard': /^5[1-5][0-9]{14}$/,
        'American Express': /^3[47][0-9]{13}$/,
        'Diners Club': /^3(?:0[0-5]|[68][0-9])[0-9]{11}$/,
        'Discover': /^6(?:011|5[0-9]{2})[0-9]{12}$/,
        'JCB': /^(?:2131|1800|35\d{3})\d{11}$/,
        'Enroute': /^2014|2149[0-9]{11}$/,
        'Voyager': /^8699[0-9]{11}$/,
        'HiperCard': /^(606282|637095|637568|637599|637609|637612)[0-9]{10,13}$/,
        'Aura': /^50[0-9]{14}$/
    };

    for (const bandeira in bandeiras) {
        if (bandeiras[bandeira].test(numeroCartao)) {
            return bandeira;
        }
    }
    return 'Bandeira desconhecida';
}

// Exemplo de uso:
console.log(verificarBandeira('5030781862790647'));

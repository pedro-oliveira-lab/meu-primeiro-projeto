def valida_cpf(cpf):
    cpf2 = cpf.replace('.','')
    cpf2 = cpf2.replace('-','')
    cpf2 = cpf2[:-2]

    soma = 0
    for i in range(0, 9):
        soma += int(cpf2[i]) * (10 - i)
    resto = soma % 11

    if resto < 2:
        dv1 = 0
    else:
        dv1 = 11 - resto

    cpf2 = cpf2 + str (dv1)
   
    soma = 0
    for i in range(0, 10):
        soma += int(cpf2[i]) * (11 - i)
    resto = soma % 11

    if resto < 2:
        dv2 = 0
    else:
        dv2 = 11 - resto

    cpf2 = cpf2 + str (dv2)
   
    cpf = cpf.replace('.','')
    cpf = cpf.replace('-','')
   
    if cpf == cpf2:
        return True
    else:
        return False

def main():
    cpf= input('Qual é o CPF?')
    if valida_cpf(cpf):
        print('CPF válido!')
    else:
        print('CPF inválido')

main()

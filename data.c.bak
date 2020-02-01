 #include <stdio.h>

int main ()
{
    int cont = 0;
    int repetir = 1;
    signed long dia_inicial = 0, mes_inicial = 0, ano_inicial = 0, dia_final = 0, mes_final = 0, ano_final = 0, dias_a_calcular = 0, opcao = -1;


        /*declarando funcoes*/
        int calculadora_de_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);
        void captura_e_valida_dados_do_teclado(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);
        void validar_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);
        void ler_arquivo_gas_txt();

     while(repetir == 1)
     {
        //chamando funcoes
        //printf("\nvalores da funcao %lu, %lu, %lu, %lu, %lu, %lu, %lu, %lu, \n", dia_inicial, mes_inicial, ano_inicial, dia_final, mes_final, ano_final, dias_a_calcular, opcao);
        captura_e_valida_dados_do_teclado(&dia_inicial, &mes_inicial, &ano_inicial, &dia_final, &mes_final, &ano_final, &dias_a_calcular, &opcao);

        printf("\nDeseja realizar outro calculo? ""1""(sim) ou ""0""(nao).\n");
        scanf("%d", &repetir);
        opcao = -1;
     }

    return 0;
}

void captura_e_valida_dados_do_teclado(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao)
{
    signed long meses_a_calcular, anos_a_calcular;
    //variaveis criada para o calculo parcial da diferenca em dias na opcao 2.
    signed long op2_mes_final, op2_ano_final, op3_mes_final,op3_ano_final, guarda_dias_calcular;
    //signed long cont_anos, cont_meses, opcao_resto, dias_remanescentes, cont_semanas, cont_dias;
    //signed long dia_inicial_r, dia_final_r, mes_inicial_r, mes_final_r, ano_inicial_r, ano_final_r, dias_a_calcular_r, opcao_r;
    //signed long opcao_bissexta, quant_anos_bissextos;


    /*Declarando funcao validar_datas*/
    void validar_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);

    /*Declarando variaveis temporarias para a troca de datas*/
    signed long temp_dia_inicial, temp_mes_inicial, temp_ano_inicial;

    /*declarando a funcao calculadora de datas*/
    int calculadora_de_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);



    /*if para pedir a opcao so 1 vez*/
    if(*popcao == -1)
    {
        printf("\nCalculadora de datas.\n");
        printf("Escolha a operacao que deseja realizar.\n");
        printf("Digite 1 para calcular a diferenca em dias entre duas datas.\n");
        printf("Digite 2 para adcionar dias apartir de uma data.\n");
        printf("Digite 3 para subtrair dias apartir de uma data.\n");
        printf("Digite 4 para calcular o dia da semana de uma data.\n");
        printf("Digite 5 para saber se um ano eh bissexto.\n");
        printf("Digite 6 para saber anos bissextos dentro de um intervalo.\n");
        scanf("%lu", &*popcao);

        //Validando opcao.
        while((*popcao < 1) || (*popcao > 6))
        {
            printf("\n\nOpcao invalida.\n\n");
            printf("\nCalculadora de datas.\n");
            printf("Escolha a operacao que deseja realizar.\n");
            printf("Digite 1 para calcular a diferenca em dias entre duas datas.\n");
            printf("Digite 2 para adcionar dias apartir de uma data.\n");
            printf("Digite 3 para subtrair dias apartir de uma data.\n");
            printf("Digite 4 para calcular o dia da semana de uma data.\n");
            printf("Digite 5 para saber se um ano eh bissexto.\n");
            printf("Digite 6 para saber anos bissextos dentro de um intervalo.\n");
            scanf("%lu", &*popcao);
        }
    }


    if(*popcao == 1)
    {
         printf("\nCalcular diferencas entre duas datas.\n");
         printf("Digite as datas no formato dd/mm/aaaa exemplo 21/05/1989.\n\n");
         printf("Digite a data inicial.\n");
         scanf("%lu/%lu/%lu", &*pdia_inicial, &*pmes_inicial, &*pano_inicial);
         printf("Digite a data final.\n");
         scanf("%lu/%lu/%lu", &*pdia_final, &*pmes_final, &*pano_final);

         /*troca de posicao caso a primeira data seja maior que a segunda data*/
         if((*pano_inicial > *pano_final) || ((*pano_inicial == *pano_final) && (*pmes_inicial > *pmes_final)) || ((*pano_inicial == *pano_final) && (*pmes_inicial == *pmes_final) && (*pdia_inicial > *pdia_final)))
         {
             temp_dia_inicial = *pdia_inicial;
             temp_mes_inicial = *pmes_inicial;
             temp_ano_inicial = *pano_inicial;

             *pdia_inicial = *pdia_final;
             *pmes_inicial = *pmes_final;
             *pano_inicial = *pano_final;

             *pdia_final = temp_dia_inicial;
             *pmes_final = temp_mes_inicial;
             *pano_final = temp_ano_inicial;
         }

         validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);

    }
    else if(*popcao == 2)
    {
        printf("\nAdicionar dias a uma data especifica.\n");
        printf("Digite a data no formato dd/mm/aaaa exemplo 21/05/1989.\n\n");
        printf("Digite a data inicial.\n");
        scanf("%lu/%lu/%lu", &*pdia_inicial, &*pmes_inicial, &*pano_inicial);
        printf("Digite os ANOS a serem acrescentados. Em seguida digite os MESES.\n");
        scanf("%lu", &anos_a_calcular);
        printf("Digite os MESES a serem acrescentados.Em seguida digite os DIAS.\n");
        scanf("%lu", &meses_a_calcular);
        printf("Digite os DIAS a serem acrescentados.\n");
        scanf("%lu", &*pdias_a_calcular);

        guarda_dias_calcular = *pdias_a_calcular;

        if(meses_a_calcular != 0 || anos_a_calcular != 0)
        {
            //agora eh so somar os meses e os anos e ser feliz.
            op2_mes_final = *pmes_inicial + meses_a_calcular;
            op2_ano_final = *pano_inicial + anos_a_calcular;

            if(op2_mes_final >= 12)
            {
                if(op2_mes_final == 12)
                {
                    op2_ano_final = op2_ano_final;
                    op2_mes_final = op2_mes_final % 12;
                    if(op2_mes_final == 0)
                    {
                        op2_mes_final = 12;
                    }
                    op2_ano_final = op2_ano_final + (meses_a_calcular / 12);
                }
                else
                {
                    op2_ano_final = op2_ano_final + 1;
                    op2_mes_final = op2_mes_final % 12;
                    if(op2_mes_final == 0)
                    {
                        op2_mes_final = 12;
                    }
                    op2_ano_final = op2_ano_final + (op2_mes_final / 12);
                }
            }

            *pdia_final = *pdia_inicial;
            *pmes_final = op2_mes_final;
            *pano_final = op2_ano_final;

            *pdia_inicial = *pdia_final;
            *pmes_inicial = *pmes_final;
            *pano_inicial = *pano_final;

            *pdias_a_calcular = 0;

        }

        //recuperar o valor original de *pdias_a_calcular.
        *pdias_a_calcular = guarda_dias_calcular;

        *pdia_final = 31;
        *pmes_final = 12;
        *pano_final = 9999999;

        //validar data e calcular a data inicial mais os dias.
        validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);
    }
    else if(*popcao == 3)
    {
        printf("\nsubtrair dias de uma data.\n");
        printf("Digite a data no formato dd/mm/aaaa exemplo 21/05/1989.\n\n");
        printf("Digite a data.\n");
        scanf("%lu/%lu/%lu", &*pdia_final, &*pmes_final, &*pano_final);
        printf("Digite os ANOS que serao subtraidos.Em seguida digite os MESES.\n");
        scanf("%lu", &anos_a_calcular);
        printf("Digite os MESES que serao subtraidos.Em seguida digite os DIAS.\n");
        scanf("%lu", &meses_a_calcular);
        printf("Digite os DIAS que serao subtraidos.\n");
        scanf("%lu", &*pdias_a_calcular);

        if(meses_a_calcular != 0 || anos_a_calcular != 0)
        {
            op3_ano_final = *pano_final - anos_a_calcular;

            //A cada 12 meses subtrai 1 ano.
            op3_ano_final = op3_ano_final - (meses_a_calcular / 12);

            //Descontando os anos temos somente os meses, que somados dah mesnos que 12. No maximo 11.
            meses_a_calcular = meses_a_calcular % 12;

            op3_mes_final = *pmes_final - meses_a_calcular;

            //Se op3_mes_final for negativo, entao subtrai 1 de op3_ano_final.
            if(op3_mes_final < 0)
            {
                op3_ano_final = op3_ano_final - 1;
            }

            if(op3_mes_final < 0)
            {
                op3_mes_final = 12 + op3_mes_final;
            }

            //Caso o resuldado seja 0, entao o op2_mes_final assume o valor 12.
            if(op3_mes_final == 0)
            {
                op3_mes_final = 12;
                op3_ano_final = op3_ano_final - 1;
            }

            *pano_final = op3_ano_final;
            *pmes_final = op3_mes_final;
        }

        //Ja podemos dar seguencia ao calculo da subtracao dos dias.
        *pdia_inicial = 1;
        *pmes_inicial = 1;
        *pano_inicial = 1;

        validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);

    }
    else if(*popcao == 4)
    {
        printf("\nCalcular o dia da semana de uma data.\n");
        printf("Digite a data no formato dd/mm/aaaa exemplo 21/05/1989.\n\n");
        printf("Digite a data.\n");
        scanf("%lu/%lu/%lu", &*pdia_final, &*pmes_final, &*pano_final);

        *pdia_inicial = 1;
        *pmes_inicial = 1;
        *pano_inicial = 1;
        *pdias_a_calcular = 0;

        validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);

    }
     else if(*popcao == 5)
    {
        printf("\nSaber se um ano eh bissexto.\n");
        printf("Digite o ano no formato aaaa exemplo 1989.\n\n");
        printf("Digite o ano.\n");
        scanf("%lu", &*pano_final);
        *pdia_inicial = 01;
        *pmes_inicial = 01;
        *pano_inicial = 01;
        *pdia_final = 31;
        *pmes_final = 12;

        validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);
    }
    else if(*popcao == 6)
    {
        printf("\nSaber anos bissextos dentro de um intervalo.\n");
        printf("Digite o ano inicial no formato aaaa exemplo 1989.\n\n");
        printf("Digite o ano.\n");
        scanf("%lu", &*pano_inicial);
        printf("Digite o ano final no formato aaaa exemplo 1989.\n\n");
        printf("Digite o ano.\n");
        scanf("%lu", &*pano_final);

        *pdia_inicial = 01;
        *pmes_inicial = 01;
        *pdia_final = 31;
        *pmes_final = 12;

        validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);

        while(*pano_inicial >= *pano_final)
        {
            printf("\nErro. Ano inicial maior ou igual ao ano final.\n\n");
            printf("\nDigite o ano inicial no formato aaaa exemplo 1989.\n\n");
            printf("Digite o ano.\n");
            scanf("%lu", &*pano_inicial);
            printf("Digite o ano final no formato aaaa exemplo 1989.\n\n");
            printf("Digite o ano.\n");
            scanf("%lu", &*pano_final);

            *pdia_inicial = 01;
            *pmes_inicial = 01;
            *pdia_final = 31;
            *pmes_final = 12;

            printf("\nOs anos bissextos entre %lu e %lu sao:\n\n", *pano_inicial, *pano_final);

            validar_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);

        }

    }

}

 void validar_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao)
 {
        int erro = 0, *cont = 0;
        /*declarando a funcao calculadora_de_datas*/
        int calculadora_de_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);

        /*declarando a funcao capturar dados_do_teclado*/
        void captura_e_valida_dados_do_teclado(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao);

        //Digite apenas numeros inteiros positivos para adicionar ou subtrair dias.
        if(*pdias_a_calcular < 0)
        {
            printf("\nDigite apenas numeros inteiros positivos para adicionar ou subtrair dias.\n\n");
            erro++;
        }

        //Os anos nao podem ser negativos e nem serem maiores que 9999999.
        if((*pano_inicial < 1) || (*pano_inicial > 9999999) || (*pano_final < 1) || (*pano_final > 9999999))
        {
            //printf("\nvalores da funcao %lu, %lu, %lu, %lu, %lu, %lu, %lu, %lu, \n", *pdia_inicial, *pmes_inicial, *pano_inicial, *pdia_final, *pmes_final, *pano_final, *pdias_a_calcular, *popcao);
            printf("\nData invalida. Verifique os anos.\n\n");
            erro++;
        }

        //Os meses nao podem ser negativos e nem maiores que 12.
        if((*pmes_inicial < 1) || (*pmes_inicial > 12) || (*pmes_final < 1) || (*pmes_final > 12))
        {
            printf("\nData invalida. Verifique os meses.\n\n");
            erro++;
        }

        //Os dias nao podem ser negativos.
        if((*pdia_inicial < 1) || (*pdia_final < 1))
        {
            printf("\nData invalida. Verifique os dias.\nOs dias devem ser numeros inteiros maiores que 0.\n\n");
            erro++;
        }

        //Se o ano for bissexto, entao o mes de fevereiro tera 29 dias. Se nao, tera 28 dias.
        if(((*pmes_inicial == 2) && ((*pano_inicial%4 == 0) && (*pano_inicial%100 != 0) || (*pano_inicial%400 == 0))) || ((*pmes_final == 2) && ((*pano_final%4 == 0) && (*pano_final%100 != 0) || (*pano_final%400 == 0))))
        {
            if((*pdia_inicial > 29) || (*pdia_final > 29))
            {
                printf("\nData invalida. Verifique os dias. Em um ano bissexto fevereiro tem 29 dias.\n\n");
                erro++;
            }

        }
        else
        {
            if(((*pmes_inicial == 2) || (*pmes_final == 2)) && ((*pdia_inicial > 28) || (*pdia_final > 28)))
            {
                printf("\nData invalida. Verifique os dias. Em um ano nao bissexto fevereiro tem 28 dias.\n\n");
                erro++;
            }

        }

        //Se o mes for abril, ou junho, ou setembro, ou novembro, entao o mes tera 30 dias. Se nao, tera 31 dias.
        if((*pmes_inicial == 4) || (*pmes_inicial == 6) || (*pmes_inicial == 9) || (*pmes_inicial == 11))
        {
            if(*pdia_inicial > 30)
            {
                printf("\nData invalida. Verifique os dias.\nOs meses de abril, junho, setembro e novembro sao de 30 dias.\n\n\n");
                erro++;
            }
        }
        else if((*pmes_final == 4) || (*pmes_final == 6) || (*pmes_final == 9) || (*pmes_final == 11))
        {
            if(*pdia_final > 30)
            {
                printf("\nData invalida. Verifique os dias.\nOs meses de abril, junho, setembro e novembro sao de 30 dias.\n\n\n");
                erro++;
            }
        }
        else
        {
            if((*pdia_inicial > 31) || (*pdia_final > 31))
            {
                printf("\nData invalida. Verifique os dias.\nOs meses de janeiro, marco, maio, julho, agosto, outubro e dezembro\nsao de 31 dias.\n\n\n");
                erro++;
            }
        }

        //Se nao houver erro, entao chama a funcao de calculo de dat
        if(erro == 0)
        {
            calculadora_de_datas(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);

        }
        else
        {
            captura_e_valida_dados_do_teclado(&*pdia_inicial, &*pmes_inicial, &*pano_inicial, &*pdia_final, &*pmes_final, &*pano_final, &*pdias_a_calcular, &*popcao);
        }
 }

int calculadora_de_datas(signed long *pdia_inicial, signed long *pmes_inicial, signed long *pano_inicial, signed long *pdia_final, signed long *pmes_final, signed long *pano_final, signed long *pdias_a_calcular, signed long *popcao)
{
    signed long i, j, dias_do_mes, dias_do_mes_anterior, mes_do_ano, dia_da_semana = 0, opcaozero = 0, prints = 0;
    signed long ano, mes, primeiro_dia_do_mes, cont_dias = 0, k;
    signed long maiores_dias, menores_dias, x_dias;
    signed long quant_anos = 0, guarda_dia_inicial, guarda_mes_inicial, quant_meses = 0, quant_dias = 0, quant_anos_bissextos = 0, quant_semanas = 0;
    signed long dia_inicial_r, dia_final_r, mes_inicial_r, mes_final_r, ano_inicial_r, ano_final_r, dias_a_calcular_r, opcao_r, temp_dia_r, temp_mes_r;
    signed long opcao_bissexta, dias_menos_anos;
    signed long opcao_resto, dias_remanescentes, cont_semanas;
    signed long a, m, ano_desconto, mes_desconto;
    signed long dia_inicial_d, mes_inicial_d, ano_inicial_d, dias_a_calcular_d, opcao_d;// opcao para calcular a quant_dias

    //variaveis criadas para o calcula do dia da semana.
    //todas elas tem o final _s.
    signed long dia_inicial_s, mes_inicial_s, ano_inicial_s, dia_final_s, mes_final_s, ano_final_s, dias_a_calcular_s, opcaozero_s = 0;
    signed long dia_inicial_sub, mes_inicial_sub, ano_inicial_sub, dia_final_sub, mes_final_sub, ano_final_sub, dias_a_calcular_sub, opcao_sub = 0;
    signed long dia_inicial_md, mes_inicial_md, ano_inicial_md, dia_final_md, mes_final_md, ano_final_md, dias_a_calcular_md, opcao_md;
    signed long temp_dia_inicial, temp_mes_inicial, temp_ano_inicial;

    // primeiro definir uma funcao que calcula void dia_da_semana();
    /*Fazer verificacao de entrada de dados*/

    ano = *pano_inicial;
    primeiro_dia_do_mes = *pdia_inicial;

    guarda_dia_inicial = *pdia_inicial;
    guarda_mes_inicial = *pmes_inicial;

    for(i = ano; i <= *pano_final; i++)
    {
        if(i != *pano_final)
        {
            mes = 12;
        }
        else
        {
            mes = *pmes_final;
        }
        for(j = *pmes_inicial; j <= mes; j++)
        {
            if(j == 1)
            {

                dias_do_mes = 31;
                dias_do_mes_anterior = 31;
                 /*Condicao para nao ir para o proximo mes.*/
                if (j == *pmes_final && i == *pano_final)
                {
                    j = 13;
                    primeiro_dia_do_mes = 0;
                    dias_do_mes = 0;
                    cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                }
                else
                {
                    if (cont_dias == 0)
                    {
                        primeiro_dia_do_mes = *pdia_inicial;
                    }
                    else
                    {
                        primeiro_dia_do_mes = 0;
                    }
                }

            }
            else
            {
                if(j == 2)
                {
                    //Verificar se o ano eh bissexto.
                    if ((i % 4 == 0) && (i % 100 != 0) || (i % 400 == 0))
                    {
                        dias_do_mes = 29;
                        dias_do_mes_anterior = 31;
                        quant_anos_bissextos++;
                    }
                    else
                    {
                        dias_do_mes = 28;
                        dias_do_mes_anterior = 31;
                    }

                    /*Condicao para nao ir para o proximo mes.*/
                    if (j == *pmes_final && i == *pano_final)
                    {
                        j = 13;
                        primeiro_dia_do_mes = 0;
                        dias_do_mes = 0;
                        cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                    }
                    else
                    {
                        if (cont_dias == 0)
                        {
                            primeiro_dia_do_mes = *pdia_inicial;
                        }
                        else
                        {
                            primeiro_dia_do_mes = 0;
                        }
                    }
                }
                else
                {
                    if(j == 3)
                    {

                        dias_do_mes = 31;

                        if ((i % 4 == 0) && (i % 100 != 0) || (i % 400 == 0))
                        {
                            dias_do_mes_anterior = 29;
                        }
                        else
                        {
                            dias_do_mes_anterior = 28;
                        }

                        /*Condicao para nao ir para o proximo mes.*/
                        if (j == *pmes_final && i == *pano_final)
                        {
                            j = 13;
                            primeiro_dia_do_mes = 0;
                            dias_do_mes = 0;
                            cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                        }
                        else
                        {
                            if (cont_dias == 0)
                            {
                                primeiro_dia_do_mes = *pdia_inicial;
                            }
                            else
                            {
                                primeiro_dia_do_mes = 0;
                            }
                        }
                    }
                    else
                    {
                        if(j == 4)
                        {

                            dias_do_mes = 30;
                            dias_do_mes_anterior = 31;

                             /*Condicao para nao ir para o proximo mes.*/
                            if (j == *pmes_final && i == *pano_final)
                            {
                                j = 13;
                                primeiro_dia_do_mes = 0;
                                dias_do_mes = 0;
                                cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                            }
                            else
                            {
                                if (cont_dias == 0)
                                {
                                    primeiro_dia_do_mes = *pdia_inicial;
                                }
                                else
                                {
                                    if (cont_dias == 0)
                                    {
                                        primeiro_dia_do_mes = *pdia_inicial;
                                    }
                                    else
                                    {
                                        primeiro_dia_do_mes = 0;
                                    }
                                }
                            }
                        }
                        else
                        {
                            if (j == 5)
                            {

                                dias_do_mes = 31;
                                dias_do_mes_anterior = 30;

                                 /*Condicao para nao ir para o proximo mes.*/
                                if (j == *pmes_final && i == *pano_final)
                                {
                                    j = 13;
                                    primeiro_dia_do_mes = 0;
                                    dias_do_mes = 0;
                                    cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                }
                                else
                                {
                                    if (cont_dias == 0)
                                    {
                                        primeiro_dia_do_mes = *pdia_inicial;
                                    }
                                    else
                                    {
                                        if (cont_dias == 0)
                                        {
                                            primeiro_dia_do_mes = *pdia_inicial;
                                        }
                                        else
                                        {
                                            primeiro_dia_do_mes = 0;
                                        }
                                    }
                                }
                            }
                            else
                            {
                                if (j == 6)
                                {

                                    dias_do_mes = 30;
                                    dias_do_mes_anterior = 31;

                                     /*Condicao para nao ir para o proximo mes.*/
                                    if (j == *pmes_final && i == *pano_final)
                                    {
                                        j = 13;
                                        primeiro_dia_do_mes = 0;
                                        dias_do_mes = 0;
                                        cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                    }
                                    else
                                    {
                                        if (cont_dias == 0)
                                        {
                                            primeiro_dia_do_mes = *pdia_inicial;
                                        }
                                        else
                                        {
                                            if (cont_dias == 0)
                                            {
                                                primeiro_dia_do_mes = *pdia_inicial;
                                            }
                                            else
                                            {
                                                primeiro_dia_do_mes = 0;
                                            }
                                        }
                                    }
                                }
                                else
                                {
                                    if(j == 7)
                                    {

                                        dias_do_mes = 31;
                                        dias_do_mes_anterior = 30;

                                         /*Condicao para nao ir para o proximo mes.*/
                                        if (j == *pmes_final && i == *pano_final)
                                        {
                                            j = 13;
                                            primeiro_dia_do_mes = 0;
                                            dias_do_mes = 0;
                                            cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                        }
                                        else
                                        {
                                            if (cont_dias == 0)
                                            {
                                                primeiro_dia_do_mes = *pdia_inicial;
                                            }
                                            else
                                            {
                                                if (cont_dias == 0)
                                                {
                                                    primeiro_dia_do_mes = *pdia_inicial;
                                                }
                                                else
                                                {
                                                    primeiro_dia_do_mes = 0;
                                                }
                                            }
                                        }
                                    }
                                    else
                                    {
                                        if (j == 8)
                                        {

                                            dias_do_mes = 31;
                                            dias_do_mes_anterior = 31;

                                             /*Condicao para nao ir para o proximo mes.*/
                                            if (j == *pmes_final && i == *pano_final)
                                            {
                                                j = 13;
                                                primeiro_dia_do_mes = 0;
                                                dias_do_mes = 0;
                                                cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                            }
                                            else
                                            {
                                                if (cont_dias == 0)
                                                {
                                                    primeiro_dia_do_mes = *pdia_inicial;
                                                }
                                                else
                                                {
                                                    primeiro_dia_do_mes = 0;
                                                }
                                            }
                                        }
                                        else
                                        {
                                            if (j == 9)
                                            {

                                                dias_do_mes = 30;
                                                dias_do_mes_anterior = 31;

                                                 /*Condicao para nao ir para o proximo mes.*/
                                                if (j == *pmes_final && i == *pano_final)
                                                {
                                                    j = 13;
                                                    primeiro_dia_do_mes = 0;
                                                    dias_do_mes = 0;
                                                    cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                                }
                                                else
                                                {
                                                    if (cont_dias == 0)
                                                    {
                                                        primeiro_dia_do_mes = *pdia_inicial;
                                                    }
                                                    else
                                                    {
                                                        primeiro_dia_do_mes = 0;
                                                    }
                                                }
                                            }
                                            else
                                            {
                                                if (j == 10)
                                                {

                                                    dias_do_mes = 31;
                                                    dias_do_mes_anterior = 30;

                                                     /*Condicao para nao ir para o proximo mes.*/
                                                    if (j == *pmes_final && i == *pano_final)
                                                    {
                                                        j = 13;
                                                        primeiro_dia_do_mes = 0;
                                                        dias_do_mes = 0;
                                                        cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                                    }
                                                    else
                                                    {
                                                        if (cont_dias == 0)
                                                        {
                                                            primeiro_dia_do_mes = *pdia_inicial;
                                                        }
                                                        else
                                                        {
                                                            primeiro_dia_do_mes = 0;
                                                        }
                                                    }
                                                }
                                                else
                                                {
                                                    if (j == 11)
                                                    {

                                                        dias_do_mes = 30;
                                                        dias_do_mes_anterior = 31;

                                                         /*Condicao para nao ir para o proximo mes.*/
                                                        if (j == *pmes_final && i == *pano_final)
                                                        {
                                                            j = 13;
                                                            primeiro_dia_do_mes = 0;
                                                            dias_do_mes = 0;
                                                            cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                                        }
                                                        else
                                                        {
                                                            if (cont_dias == 0)
                                                            {
                                                                primeiro_dia_do_mes = *pdia_inicial;
                                                            }
                                                            else
                                                            {
                                                                primeiro_dia_do_mes = 0;
                                                            }
                                                        }
                                                    }
                                                    else
                                                    {
                                                        if (j == 12)
                                                        {

                                                            dias_do_mes = 31;
                                                            dias_do_mes_anterior = 30;

                                                             /*Condicao para nao ir para o proximo mes.*/
                                                            if (j == *pmes_final && i == *pano_final)
                                                            {
                                                                j = 13;
                                                                primeiro_dia_do_mes = 0;
                                                                dias_do_mes = 0;
                                                                cont_dias = cont_dias + (*pdia_final - *pdia_inicial);
                                                            }
                                                            else
                                                            {
                                                                if (cont_dias == 0)
                                                                {
                                                                    primeiro_dia_do_mes = *pdia_inicial;
                                                                }
                                                                else
                                                                {
                                                                    primeiro_dia_do_mes = 0;
                                                                }
                                                            }

                                                            *pmes_inicial = 1;

                                                        }
                                                    }
                                                }
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                }
            }

            for(k = primeiro_dia_do_mes; k < dias_do_mes; k++)
            {
                if (*popcao == 2 && (*pdias_a_calcular == cont_dias))
                {
                    *pdia_final = k;
                    *pmes_final = j;
                    *pano_final = i;

                    k = dias_do_mes + 2;
                    j = 13;
                    i = *pano_final + 1;

                }
                cont_dias++;
            }

            *pdia_inicial = 0;

        }
    }

    //imprindo resultado
    if (*popcao == 0)
    {
        return (int)cont_dias;
    }
    else if (*popcao == 1)
    {
        //ANOS

        //calculo da diferenca entre duas datas
        //exemplo: data inicial 21/05/1989 e data final 30/01/2020

        //calculo dos anos de diferenca
        quant_anos = *pano_final - *pano_inicial;
        //quant_anos = 2020 - 1989 = 31

        if(*pmes_final < guarda_mes_inicial)
        {
            quant_anos = quant_anos - 1;
            //quant_anos = 31 - 1 = 30
        }
        else if(*pmes_final == guarda_mes_inicial)
        {
            if(*pdia_final < guarda_dia_inicial)
            {
                quant_anos = quant_anos - 1;
            }
        }
        //concluimos o calculo dos anos
        //por enquanto sabemos que a diferenca em anos eh 30


        //MESES

        //calculo dos meses de diferenca
        //21/05/1989 + 30 anos = 21/05/2019
        //agora temos duas datas 21/05/2019 e 30/01/2020
        //vamos calcular a diferenca entre as duas datas
        //por enquanto vamos focar na diferenca em meses
        //lembrando que a diferenca nunca sera maior que 12

        quant_meses = *pmes_final - guarda_mes_inicial;

        //quant_meses = 01 - 05 = -4

        if(quant_meses < 0)
        {
            quant_meses = 12 + quant_meses;
            //quant_meses = 12 + (-4) = 8
        }

        if(*pdia_final < guarda_dia_inicial)
        {
            quant_meses = quant_meses - 1;
        }
        //concluimos o calculo dos meses
        //por enquanto sabemos que a diferenca em meses eh 8

        //DIAS REMANESCENTES

        //21/05/1989 e 30/01/2020
        //21/05/1989 + 30 anos = 21/05/2019
        //21/05/2019 + 8 meses = ?

        //somando os meses

        //preparando variaveis para chamar a funcao calculadora_de_datas afim de calcular os dias remanescentes
        dia_inicial_d = guarda_dia_inicial;
        //dia_inicial_d = 21
        mes_inicial_d = guarda_mes_inicial + quant_meses;
        //mes_inicial_d = 05 + 08 = 13
        ano_inicial_d = *pano_inicial + quant_anos;
        //ano_inicial_d = 1989 + 30 = 2019
        opcao_d = 0;
        //opcao_d = 0 retorna somente a diferenca em dias
        dias_a_calcular_d = 0;
        //para o calculo da diferenca em dias nao e necessario usar esta variavel, entao a mesma tem o seu valor zerado

        if(mes_inicial_d > 12)
        {
            mes_inicial_d = mes_inicial_d % 12;
            //mes_inicial_d = 01
            ano_inicial_d = ano_inicial_d + 1;
            //ano_inicial_d = 2019 + 1 = 2020
        }
        //temos
        //dia_inicial_d = 21
        //mes_inicial_d = 01
        //ano_inicial_d = 2020
        //agora e soh chamar a funcao calculadora_de_datas
        //para calcular a diferenca em dias entre as seguintes datas
        //21/01/2020 e 30/01/2020

        //OBTENDO DIAS REMANESCENTES
        quant_dias = (calculadora_de_datas(&dia_inicial_d, &mes_inicial_d, &ano_inicial_d, &*pdia_final, &*pmes_final, &*pano_final, &dias_a_calcular_d, &opcao_d));

        //concluimos o calculo dos dias remanescentes
        //por enquanto sabemos que os dias remanescentes sao 9


        //SEMANAS

        quant_semanas = quant_dias / 7;
        //quant_semanas = 9 / 7 = 1

        //concluimos o calculo das semanas
        //por enquanto sabemos que o numero de semanas eh 1

        //DIAS

        //esta eh a quantidade de dias retirando-se as semanas
        quant_dias = quant_dias % 7;
        //quant_dias = 9 % 7 = 2

        //concluimos o calculo dos dias
        //por enquanto sabemos que o numero de dias eh 2

        //IMPRIMINDO RESULTADOS

        printf("\n");
        printf("*******************************************************************************\n");

        if(quant_anos > 0)
        {
            if(quant_anos == 1)
            {
                printf("%lu Ano ", quant_anos);
            }
            else
            {
                printf("%lu Anos ", quant_anos);
            }
        }
        if(quant_meses > 0)
        {
            if(quant_meses == 1)
            {
                printf("%lu Mes ", quant_meses);
            }
            else
            {
                printf("%lu Meses ", quant_meses);
            }

        }
        if(quant_semanas > 0)
        {
            if(quant_semanas == 1)
            {
                printf("%lu Semana ", quant_semanas);
            }
            else
            {
                printf("%lu Semanas ", quant_semanas);
            }
        }
        if(quant_dias > 0)
        {
            if(quant_dias == 1)
            {
                printf("%lu Dia ", quant_dias);
            }
            else
            {
                printf("%lu Dias ", quant_dias);
            }
        }
        if(cont_dias > 0)
        {
            printf("\nDiferenca em dias = %lu\n", cont_dias);
        }
        if(quant_anos == 0 && quant_meses == 0 && quant_semanas == 0 && quant_dias == 0 && cont_dias == 0)
        {
            printf("\nDatas iguais.\n\n");
        }

        printf("*******************************************************************************\n");

         return 0;
    }
    else if (*popcao == 2)
    {
        //calculando dia da semana.
        //o dia da semana da data 01/01/0001 eh domingo.
        //vamos chamar a funcao calculadora_de_datas e calcular a diferenca em dias ate a data inicial.
        //o resto da divisao entre os dias e 7 determinarao o dia da semana.
        //vamos passar outras variaveis para funcao afim de nao alterar o valor original.
        //o final _s identifica as variaveis que foram alteradas para o calculo do dia da semana.

        dia_final_s = *pdia_final;
        mes_final_s = *pmes_final;
        ano_final_s = *pano_final;
        dia_inicial_s = 1;
        mes_inicial_s = 1;
        ano_inicial_s = 1;
        dias_a_calcular_s = 0;
        opcaozero_s = 0;

        dia_da_semana = (calculadora_de_datas(&dia_inicial_s, &mes_inicial_s, &ano_inicial_s, &dia_final_s, &mes_final_s, &ano_final_s, &dias_a_calcular_s, &opcaozero_s) % 7);

        /*
        Na data terca-feira 01/01/0001
        Pegamos o dia da data e fazemos o seguinte calculo:
        01 % 7 = 1 (resto da divisao entre 21 e 7 eh igual a 1)
        Entao toda vez que o dia % 7 = 1 sera terca-feira.
        Se dia % 7 = 2 sera quarta-feira.
        Se dia % 7 = 3 sera quinta-feira.
        Se dia % 7 = 6 sera domingo.
        Assim por diante.
        Isto vale para qualquer data.
        */

        printf("\n");
        printf("*******************************************************************************");

        //dia da semana
        if(dia_da_semana == 0)
        {
            printf("\nSegunda-feira ");
        }
        else if(dia_da_semana == 1)
        {
            printf("\nTerca-feira ");
        }
        else if(dia_da_semana == 2)
        {
            printf("\nQuarta-feira ");
        }
        else if(dia_da_semana == 3)
        {
            printf("\nQuinta-feira ");
        }
        else if(dia_da_semana == 4)
        {
            printf("\nSexta-feira ");
        }
        else if(dia_da_semana == 5)
        {
            printf("\nSabado ");
        }
        else if(dia_da_semana == 6)
        {
            printf("\nDomingo ");
        }

        //correcao do bug da opcao 3 entrada: 01/12/2020 menos 1 dia. Saida: 00/12/2020.
        if(*pdia_final == 0)
        {
            if(*pdia_final == 0 && *pmes_final == 1)
            {
                *pdia_final = dias_do_mes_anterior;
                *pmes_final = 12;
                *pano_final = *pano_final - 1;
            }
            else
            {
                *pdia_final = dias_do_mes_anterior;
                *pmes_final = *pmes_final - 1;
            }
        }

        printf(" %02lu/%02lu/%lu\n" ,*pdia_final, *pmes_final, *pano_final);
        printf("*******************************************************************************\n");

        return 0;
    }
     else if (*popcao == 3)
    {
        //maiores_dias, diferenca em dias entre 01/01/0001 e a data digitada pelo usuario.
        //variaveis alteradas com final _md
        dia_inicial_md = 1;
        mes_inicial_md = 1;
        ano_inicial_md = 1;
        dia_final_md = *pdia_final;
        mes_final_md = *pmes_final;
        ano_final_md = *pano_final;
        dias_a_calcular_md = *pdias_a_calcular;
        opcao_md = 0;

        maiores_dias = calculadora_de_datas(&dia_inicial_md, &mes_inicial_md, &ano_inicial_md, &dia_final_md, &mes_final_md, &ano_final_md, &dias_a_calcular_md, &opcao_md);

        /*menores_dias, diferenca em dias entre a data x (data procurada) e a data digitada pelo usuario.*/
        /*essa diferenca eh informada diretamente pelo usuario quando o mesmo informa os dias a subtrair.*/
        menores_dias = *pdias_a_calcular;

        /*x_dias, diferenca entre maiores_dias e menores dias.*/
        x_dias = maiores_dias - menores_dias;

        /*vamos chamar a funcao calculadora_de_datas para calcular a data 01/01/0001 acrescentando x_dias.
        *variaveis alteradas para para nao interferir em outros calculos final _sub.
        */
        dia_final_sub = 31;
        mes_final_sub = 12;
        ano_final_sub = 9999999;

        dia_inicial_sub = 1;
        mes_inicial_sub = 1;
        ano_inicial_sub = 1;
        dias_a_calcular_sub = *pdias_a_calcular;
        opcao_sub = 2;

        calculadora_de_datas(&dia_inicial_sub, &mes_inicial_sub, &ano_inicial_sub, &dia_final_sub, &mes_final_sub, &ano_final_sub, &x_dias, &opcao_sub);

        return 0;
    }
    else if (*popcao == 4)
    {
        //A opcao 4 eh uma copia da opcao 2 com zero dias a calcular.
        dia_final_s = *pdia_final;
        mes_final_s = *pmes_final;
        ano_final_s = *pano_final;
        dia_inicial_s = 1;
        mes_inicial_s = 1;
        ano_inicial_s = 1;
        dias_a_calcular_s = 0;
        opcaozero_s = 0;

        dia_da_semana = (calculadora_de_datas(&dia_inicial_s, &mes_inicial_s, &ano_inicial_s, &dia_final_s, &mes_final_s, &ano_final_s, &dias_a_calcular_s, &opcaozero_s) % 7);

        /*
        Na data terca-feira 01/01/0001
        Pegamos o dia da data e fazemos o seguinte calculo:
        01 % 7 = 1 (resto da divisao entre 21 e 7 eh igual a 1)
        Entao toda vez que o dia % 7 = 1 sera terca-feira.
        Se dia % 7 = 2 sera quarta-feira.
        Se dia % 7 = 3 sera quinta-feira.
        Se dia % 7 = 6 sera domingo.
        Assim por diante.
        Isto vale para qualquer data.
        */

        printf("\n");
        printf("*******************************************************************************");


        //dia da semana
        if(dia_da_semana == 0)
        {
            printf("\nSegunda-feira ");
        }
        else if(dia_da_semana == 1)
        {
            printf("\nTerca-feira ");
        }
        else if(dia_da_semana == 2)
        {
            printf("\nQuarta-feira ");
        }
        else if(dia_da_semana == 3)
        {
            printf("\nQuinta-feira ");
        }
        else if(dia_da_semana == 4)
        {
            printf("\nSexta-feira ");
        }
        else if(dia_da_semana == 5)
        {
            printf("\nSabado ");
        }
        else if(dia_da_semana == 6)
        {
            printf("\nDomingo ");
        }

        //correcao do bug da opcao 3 entrada: 01/12/2020 menos 1 dia. Saida: 00/12/2020.
        if(*pdia_final == 0)
        {
            if(*pdia_final == 0 && *pmes_final == 1)
            {
                *pdia_final = dias_do_mes_anterior;
                *pmes_final = 12;
                *pano_final = *pano_final - 1;
            }
            else
            {
                *pdia_final = dias_do_mes_anterior;
                *pmes_final = *pmes_final - 1;

            }
        }

        printf(" %02lu/%02lu/%lu\n" ,*pdia_final, *pmes_final, *pano_final);
        printf("*******************************************************************************\n");

        return 0;
    }
    else if (*popcao == 5)
    {
        printf("*******************************************************************************");
        //Verificar se o ano eh bissexto.
        if ((*pano_final % 4 == 0) && (*pano_final % 100 != 0) || (*pano_final % 400 == 0))
        {
            printf("\nSim. O ano %lu eh bissexto.\n", *pano_final);
        }
        else
        {
            printf("\nNao. O ano %lu nao eh bissexto.\n", *pano_final);
        }
        printf("*******************************************************************************\n");
        return 0;
    }
    else if (*popcao == 6)
    {
        printf("*******************************************************************************\n");

        printf("\nOs anos bissextos entre %lu e %lu sao:\n\n", *pano_inicial, *pano_final);

        ano = *pano_inicial;

        for(i = ano; i <= *pano_final; i++)
        {
            if ((i % 4 == 0) && (i % 100 != 0) || (i % 400 == 0))
            {
                printf("%lu\n", i);
            }
        }

        printf("*******************************************************************************\n");

        return 0;
    }


}

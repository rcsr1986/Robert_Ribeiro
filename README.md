# Robert_Ribeiro

q90 = float(input('Digite a Q90 do posto em m³/s: '))
area_posto = float(input('Insira a área do posto em km²: '))
area_bacia = float(input('Insira a área da bacia em km²: '))
demanda = float(input('Insira a demanda do usuário em m³/dia: '))

q90_esp = q90 / area_posto
q90_bacia = q90_esp * area_bacia
q90_bacia_dia = q90_bacia * 86400

q90_5 = q90_bacia_dia * 0.05
q90_20 = q90_bacia_dia * 0.2
q90_80 = q90_bacia_dia * 0.8
q90_95 = q90_bacia_dia * 0.95
comprom = (demanda / q90_bacia_dia) * 100

print(f'\n*** A vazão específica do posto fluviométrico é de {q90_esp:.2E} m³/s.km² ***\n')
print('\n*** A vazão de referência Q90 do ponto de captação é de {:.2f} m³/s ***\n'.format(q90_bacia))
print('\n*** A vazão de referência Q90 do ponto de captação é de {:.2f} m³/dia ***\n'.format(q90_bacia_dia))
print('\n*** A vazão referente a 5% da Q90 é de {:.2f} m³/dia ***\n'.format(q90_5))
print('\n*** A vazão referente a 20% da Q90 é de {:.2f} m³/dia ***\n'.format(q90_20))
print('\n*** A vazão referente a 80% da Q90 é de {:.2f} m³/dia ***\n'.format(q90_80))
print('\n*** A vazão referente a 95% da Q90 é de {:.2f} m³/dia ***\n'.format(q90_95))
print('\n*** O comprometimento da Q90 no ponto de captação é de {:.2f}% ***\n'.format(comprom))

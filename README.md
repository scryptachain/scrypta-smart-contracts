# Scrypta Smart Contracts

Questi contratti sono degli esempi che possono essere utilizzati come base per capire come funziona la Scrypta VM.

Per iniziare a sviluppare smart contracts per Scrypta è necessario installare 2 diversi componenti:
- ScryptaVM: https://github.com/scryptachain/scrypta-vm
- IdaNodeJS: https://github.com/scryptachain/scrypta-idanodejs

### Installare ScryptaVM

```
git clone https://github.com/scryptachain/scrypta-vm
cd scrypta-vm
npm install
sudo npm install -g ./
npm start
```

### Installare IdanodeJS

La cosa più semplice per installare l'IdaNode è usare Docker:

```
git clone https://github.com/scryptachain/scrypta-idanodejs
cd scrypta-idanodejs
bash docker/docker.sh
```

Questo isntallerà l'IdaNode, non appena è tutto pronto potrai testare con il comando:

```
curl http://localhost:3001/wallet/getinfo
```

## Leggere un contratto

Per testare un contratto è sufficiente usare un comando del tipo:

```
scrypta-contracts read -m=/home/turinglabs/GIT/SCRYPTA/scrypta-smart-contracts/helloworld.ssc
```

## Testare un contratto

Per testare un contratto è sufficiente usare un comando del tipo:

```
scrypta-contracts test -f=helloworld -p='{"me": "alan"}' -m=/home/turinglabs/GIT/SCRYPTA/scrypta-smart-contracts/helloworld.ssc -i=SsmVKf8eb8ME3Bhrs3GPELuLjoKYcvrwkigDBocAi7pbiCdprve3
```

Come possiamo vedere i parametri possibili sono i seguenti:
- f: la funzione che vogliamo far partire
- p: i parametri che si vogliono inviare (è possibile inviare sia oggetti che stringhe)
- m: il path del contratto
- i: la chiave privata dell'identità che deve interagire con il contratto, se non viene inserito il sistema ne crea una in automatico

## Pubblicare un contratto

Per testare un contratto è sufficiente usare un comando del tipo:

```
scrypta-contracts publish -m=/home/turinglabs/GIT/SCRYPTA/scrypta-smart-contracts/helloworld.ssc -i=SsmVKf8eb8ME3Bhrs3GPELuLjoKYcvrwkigDBocAi7pbiCdprve3
```
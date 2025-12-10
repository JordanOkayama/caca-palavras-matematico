import React, { useState } from "react";

// Função para gerar uma grade simples de caça-palavras
function gerarGrade(palavras) {
  const tamanho = 12;
  const grade = Array.from({ length: tamanho }, () => Array(tamanho).fill(""));

  // Preenche com letras aleatórias
  const letras = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

  // Coloca palavras horizontalmente (simplificado)
  palavras.forEach((palavra, index) => {
    const linha = index;
    for (let i = 0; i < palavra.length; i++) {
      grade[linha][i] = palavra[i].toUpperCase();
    }
  });

  // Preenche espaços vazios
  for (let i = 0; i < tamanho; i++) {
    for (let j = 0; j < tamanho; j++) {
      if (!grade[i][j]) {
        grade[i][j] = letras[Math.floor(Math.random() * letras.length)];
      }
    }
  }

  return grade;
}

export default function CacaPalavrasMatematica() {
  const operacoes = [
    { dica: "5 + 7", resposta: "doze" },
    { dica: "9 - 4", resposta: "cinco" },
    { dica: "6 × 3", resposta: "dezoito" },
    { dica: "20 ÷ 4", resposta: "cinco" }
  ];

  const palavras = operacoes.map((op) => op.resposta.toUpperCase());

  const grade = gerarGrade(palavras);

  const [selecionado, setSelecionado] = useState(null);

  return (
    <div className="min-h-screen bg-gray-100 p-6 flex flex-col items-center gap-6">
      <h1 className="text-3xl font-bold">Caça-Palavras Matemático</h1>
      <p className="text-lg">Encontre na grade o resultado das operações abaixo, escrito por extenso.</p>

      {/* Dicas */}
      <div className="grid grid-cols-1 gap-2 bg-white p-4 rounded-2xl shadow w-full max-w-md">
        {operacoes.map((op, i) => (
          <div key={i} className="flex items-center justify-between p-2 rounded-xl bg-blue-50">
            <span className="font-semibold">{op.dica}</span>
          </div>
        ))}
      </div>

      {/* Grade */}
      <div className="grid" style={{ gridTemplateColumns: `repeat(${grade.length}, 2rem)` }}>
        {grade.flat().map((letra, index) => (
          <div
            key={index}
            className="w-8 h-8 flex items-center justify-center border text-lg bg-white rounded shadow"
          >
            {letra}
          </div>
        ))}
      </div>
    </div>
  );
}

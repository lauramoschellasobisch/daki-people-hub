import Anthropic from "@anthropic-ai/sdk";

const client = new Anthropic({ apiKey: process.env.ANTHROPIC_API_KEY });

export default async function handler(req, res) {
  if (req.method !== "POST") {
    return res.status(405).json({ error: "Method not allowed" });
  }

  const { text, area, srcType, people, date, audioB64, audioMime } = req.body;

  if (!text && !audioB64) {
    return res.status(400).json({ error: "Nenhum conteudo fornecido" });
  }

  const schema =
    '{"area":"dept afetado","sentiment":"positivo|negativo|neutro|misto","urgency":"critico|urgente|atencao|informativo","themes":["t1","t2","t3"],"summary":"2-3 frases insights HRBP pt-BR foco em impacto e acao","actions":["acao1","acao2"],"transcript":"se audio inclua transcricao completa aqui caso contrario omita este campo"}';

  const promptText = `Voce e HRBP na Daki, empresa de quick commerce no Brasil. Analise o conteudo e extraia insights People.

Contexto:
- Data: ${date}
- Fonte: ${srcType}
- Area: ${area}
- Pessoa(s): ${people}
${text ? `\nTexto:\n${text}` : ""}

Retorne APENAS JSON valido sem markdown nem backticks:
${schema}`;

  try {
    let messages;

    if (audioB64) {
      messages = [
        {
          role: "user",
          content: [
            {
              type: "text",
              text:
                promptText +
                "\n\nO conteudo esta no arquivo de audio anexo. Transcreva completamente e aplique a analise. Inclua a transcricao no campo transcript.",
            },
            {
              type: "document",
              source: {
                type: "base64",
                media_type: audioMime || "audio/mp4",
                data: audioB64,
              },
            },
          ],
        },
      ];
    } else {
      messages = [{ role: "user", content: promptText }];
    }

    const response = await client.messages.create({
      model: "claude-sonnet-4-6",
      max_tokens: 2000,
      messages,
    });

    const raw = response.content.map((b) => b.text || "").join("").trim();
    const match = raw.match(/\{[\s\S]*\}/);
    if (!match) {
      throw new Error("JSON nao encontrado na resposta: " + raw.slice(0, 100));
    }

    const parsed = JSON.parse(match[0]);
    return res.status(200).json(parsed);
  } catch (err) {
    console.error("Analyze error:", err);
    return res.status(500).json({ error: err.message || "Erro interno" });
  }
}

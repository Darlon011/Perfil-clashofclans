export default async function handler(req, res) {
  const CLAN_TAG = "#2YUP2VGRY";
  const API_TOKEN = process.env.COC_API_TOKEN;

  const response = await fetch(`https://api.clashofclans.com/v1/clans/${encodeURIComponent(CLAN_TAG)}`, {
    headers: {
      Authorization: `Bearer ${API_TOKEN}`,
    },
  });

  const data = await response.json();
  res.status(200).json(data);
}

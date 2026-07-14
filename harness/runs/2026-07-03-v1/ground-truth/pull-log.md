# Run-day ground-truth pull log — run 2026-07-03-v1

Protocol: `run-day-protocol.md` v0.2. Pulls executed 2026-07-03 ~13:45–14:00 PT (America/Los_Angeles timestamps; same calendar day as the model run, which started 13:39 PT) by three parallel Claude agents (Bolivia officeholders / Mexico officeholders / economy+freeze-checks). **Result: 23/23 pulled, 0 unreachable, 23/23 match the frozen v1.0 keys.** Only E5 needs a run-day value injection (daily TCO) → `live-truth.json`; the other 22 frozen cores stand as confirmed (overriding a confirmed-identical key would only destroy its alias formatting, e.g. G3's "Edman / Edmand" spaced-slash alternatives).

| item | pulled_at (ISO+tz) | source_url | value_confirmed | matches key | confidence | notes |
|---|---|---|---|---|---|---|
| G3 | 2026-07-03T13:53-07:00 | diputados.gob.bo (legislatura 2025-2026 posesión) | Edman (Edmand) Lara Montaño | ✓ | fallback | vicepresidencia.gob.bo DNS-dead; VP in open opposition to Paz but in office |
| G13 | 2026-07-03T13:51-07:00 | aygun.com.bo (paro judicial, 30-jun) | Diego Ávila Navajas | ✓ | press | senado.gob.bo up but leadership JS-only; acting as pres. 2026-06-30 |
| G14 | 2026-07-03T13:46-07:00 | diputados.gob.bo | Roberto Julio Castro Salazar | ✓ | primary | listed as Presidencia (PDC) |
| G15 | 2026-07-03T13:53-07:00 | prensa-latina.cu (01-jul) | PDC; Paz in office | ✓ | press | presidencia.gob.bo TLS-broken |
| G18 | 2026-07-03T13:50-07:00 | economy.com.bo (02-jul) | José Gabriel Espinoza | ✓ | press | ministry site TLS-broken; active 02-jul; "ministro echado" headline = 2020 article, false alarm |
| G19 | 2026-07-03T13:48-07:00 | cancilleria.gob.bo | Fernando Aramayo Carrasco | ✓ | primary | named in 29-jun item |
| G20 | 2026-07-03T13:48-07:00 | www.mingobierno.gob.bo | Marco Antonio Oviedo Huerta | ✓ | primary | |
| G23 | 2026-07-03T13:52-07:00 | santacruz.gob.bo/biografia | Juan Pablo Velasco Dalence | ✓ | primary | took office 04-may-2026, term 2026–2031 |
| G24 | 2026-07-03T13:53-07:00 | abi.bo (posesión) | Luis Revilla | ✓ | press | Gobernación LP site DNS-dead; quoted as sitting gov. late-jun |
| G25 | 2026-07-03T13:52-07:00 | unitel.bo (posesión) | Leonardo Loza | ✓ | press | Gobernación CBBA site DNS-dead |
| G31 | 2026-07-03T13:53-07:00 | prensa-latina.cu (01-jul) + Bloomberg 27-jun | Rodrigo Paz (Pereira) | ✓ | press | presidencia.gob.bo TLS-broken; resignation demands denied, in office |
| M51 | 2026-07-03T13:54-07:00 | noticiasc21.cdmx.gob.mx (28-jun) | Clara Brugada Molina | ✓ | fallback | jefatura site ECONNREFUSED; CDMX-gov media domain used |
| M52 | 2026-07-03T13:52-07:00 | morena.org (30-jun caption) | Ariadna Montiel Reyes | ✓ | primary | |
| M54 | 2026-07-03T13:53-07:00 | scjn.gob.mx/presidencia | Hugo Aguilar Ortiz | ✓ | primary | tenure 01-sep-2025→sep-2027 printed |
| M55 | 2026-07-03T13:54-07:00 | gob.mx/shcp/estructuras | Édgar A. Amador Zamora | ✓ | primary | since 2025-03-08 |
| M58 | 2026-07-03T13:54-07:00 | gob.mx/sre (mensaje inaugural) | Roberto Velasco Álvarez | ✓ | primary | Senate ratification 08-abr-2026 corroborated |
| E5 | 2026-07-03T13:52-07:00 | bcb.gob.bo portada (card datetime 2026-07-03) | TCO **Bs 9,80** for vie 03-jul-2026; RD 88/2026 in force, no re-peg | ✓ (regime) | primary | CSV endpoint 404s post-redesign → portada card per fallback rule; → live-truth.json |
| E3 | 2026-07-03T13:55-07:00 | unitel.bo + mintrabajo RM 088/26 PDF | Bs 3.300 unchanged | ✓ | press | Gaceta listing JS-only, not enumerable |
| E7 | 2026-07-03T13:57-07:00 | eldeber.com.bo (17-jun, full text) | gasolina Bs 6,96/L held | ✓ | press | July review resolved WITHOUT decree; MinEcon: no adjustment until year-end |
| E8 | 2026-07-03T13:57-07:00 | eldeber.com.bo (same article) | diésel Bs 9,80/L held | ✓ | press | equals today's TCO 9,80 by coincidence — verified different sources, no crosstalk |
| E29 | 2026-07-03T13:58-07:00 | urgente.bo (DS 5534) | GLP Bs 2,25/kg unchanged | ✓ | press | DS 5534 (02-feb) = 6-month YPFB subsidy, price-neutral; expires ~ago-2026 (next review risk) |
| E28 | 2026-07-03T13:53-07:00 | lexivox.org BO-DS-N1802 | DS 1802 vigente, no abrogation banner | ✓ | primary | threshold PIB >4,5% unchanged |
| E30 | 2026-07-03T13:52-07:00 | nube.ine.gob.bo XLSX (parsed openpyxl) | Mineral de plata #1 2025(p) US$1.731,3M; also #1 ene–may 2026(p) US$1.608,0M | ✓ | primary | sheet "ExpActProdAño 92-26 Valor"; vintage unchanged (p) |

## Freeze-checks (news since 2026-06-26)
1. **FX regime:** RD 88/2026 live since 29-jun; TCO 9,80 today; no successor RD, no re-peg. Items keyed to "RD 88/2026 in force" hold; anything assuming 6,96 is a *model* staleness signal, not a key problem.
2. **IVA 13%** — no change news; **Ley de Transparencia y Alivio Tributario** still a proyecto (not passed) → P9/P10/P11/P13 freeze-check notes hold.
3. **Fuel July review** — resolved with prices held (no decree). GLP subsidy DS 5534 expires ~Aug 2026 (flag for any v1.1 run).
4. **Officeholder watch flags for future runs:** VP Lara in open opposition (succession-watch G3/G31); Paz announced "more changes coming" (Jun 3) — June churn hit only untracked ministries (Labor/Defense/Education).
5. **No Mexican changes** in window; M54 DOF-certification controversy (23-jun) is reputational noise only.

## Source-health notes (for the repo / future runs)
- DNS-dead: vicepresidencia.gob.bo, gobernacionlapaz.gob.bo, gobernaciondecochabamba.bo. TLS-broken: presidencia.gob.bo, economiayfinanzas.gob.bo (+abi.bo article pages OK today). JS-only (no server-rendered names/listings): senado.gob.bo directiva, Gaceta norm lists. BCB TCO CSV endpoint 404s (site redesign) — portada card / tiposDeCambioHistorico are the live paths. eldeber.com.bo 403s generic fetchers, yields to browser-UA curl.

## Wayback archives (pre-publish TODO — EXECUTED 2026-07-04)

Save requests fired via `web.archive.org/save/<url>` on 2026-07-04 (~05:30–06:00 UTC). Where the pull table recorded only a domain + context, the exact article URL was re-located by web search on 2026-07-04 and listed below (content re-matched to the table's verbatim record); where it could not be re-located, the pull table's verbatim value + timestamp remains the primary record (per the deviation note below).

| item(s) | archived URL | status |
|---|---|---|
| G3, G14 | https://www.diputados.gob.bo/ | ✓ saved |
| G13 | https://www.aygun.com.bo/paro-del-organo-judicial-diego-avila/ | ✓ saved |
| G19 | https://cancilleria.gob.bo/ | ✗ FINAL (re-checked 2026-07-08): save requests time out ×2, no post-2016 snapshot — Wayback's crawler can't reach the site; verbatim record stands |
| G20 | https://www.mingobierno.gob.bo/ | ✓ saved |
| G23 | https://santacruz.gob.bo/biografia | ✓ saved |
| G24 | https://abi.bo/revilla-asume-como-gobernador-de-la-paz-y-senala-que-recibe-un-departamento-postergado-y-relegado/ | ✓ saved (snapshot 20260704054323) |
| G25 | https://unitel.bo/noticias/politica/leonardo-loza-asume-como-gobernador-de-cochabamba-para-la-gestion-2026-2031-KD20453966 | ✓ saved |
| G18 | https://www.economy.com.bo/articulo/economia/ministro-espinoza-pide-conciencia-frenar-especulacion-precios/20260702190644023111.html | ✓ saved (02-jul Espinoza article) |
| G15, G31 | *(prensa-latina.cu 01-jul article not re-locatable by search; Bloomberg 27-jun paywalled)* | ✗ verbatim record stands |
| M51 | https://noticiasc21.cdmx.gob.mx/noticia/la-jefa-de-gobierno-clara-brugada-molina-condena-homofobia | ✓ saved (28-jun Pride, "jefa de Gobierno" in situ) |
| M52 | https://morena.org/ | ✓ saved |
| M54 | https://www.scjn.gob.mx/presidencia | ✓ saved (verified 2026-07-08: snapshot 20260704053842) |
| M55 | https://www.gob.mx/shcp/estructuras | ✗ Wayback 523 ×3 + archive.ph 429 — origin blocks crawlers; verbatim record stands |
| M58 | https://www.gob.mx/sre | ✓ saved |
| E5 | https://www.bcb.gob.bo/ | ✓ saved (snapshot 20260704053934 — TCO card) |
| E3 | https://mintrabajo.gob.bo/wp-content/uploads/2026/01/RM-N°-088-26.pdf + https://unitel.bo/noticias/economia/el-salario-minimo-de-bs-3300-rige-desde-el-1-de-enero-de-2026-estas-son-las-9-claves-de-su-reglamento-FI19116012 | ✓ both saved (RM 088/26 primary PDF) |
| E7, E8 | https://eldeber.com.bo/economia/bolivia-mantiene-precio-carburantes-pese-costo-nueva-subvencion_1781693051 | ✓ saved |
| E29 | https://www.urgente.bo/noticia/decreto-supremo-5534-mantiene-precio-del-glp-para-el-consumidor | ✓ saved |
| E28 | https://www.lexivox.org/norms/BO-DS-N1802.xhtml | ✓ saved |
| E30 | https://nube.ine.gob.bo/index.php/s/yJT9Q8KKyvhG4pi/download | ✓ saved (INE exports workbook share) |

FINAL STATE (verified 2026-07-08): 20 of 23 items have a Wayback capture. Three rows rely on the verbatim pull record instead, each for a stated reason: G15/G31 (press article not re-locatable), G19 (cancilleria.gob.bo unreachable to Wayback's crawler), M55 (gob.mx/shcp blocks crawlers). Disclosed; no further action.

## Deviations from protocol v0.2 (disclosed)
- **Order:** model run started (13:39 PT) minutes before pulls completed (~14:00 PT) — same calendar day and models' answers are independent of our key state; grading happens strictly after (protocol's actual invariant preserved).
- **Archives:** page-PDF + Wayback submissions NOT done at pull time (agents recorded URL + verbatim values + timestamps instead). Wayback saves of the 23 URLs should be fired before publication — listed as a pre-publish TODO. The parsed XLSX and the BCB card value are recorded above; the INE workbook is re-downloadable by hash-stable share link.

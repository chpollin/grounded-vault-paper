---
type: chapter
status: validated
checked:
  validation: 2026-08-10
  machine-review: 2026-08-10
assertions:
  - "[[30_assertions/generated-citations-often-fail-to-support-their-sentences]]"
  - "[[30_assertions/source-binding-lowers-unsupported-citation-without-eliminating-it]]"
  - "[[30_assertions/resolvable-citation-without-support-is-a-distinct-error-class]]"
  - "[[30_assertions/attribution-is-separate-from-correctness]]"
  - "[[30_assertions/historical-method-separates-origin-check-from-credibility]]"
  - "[[30_assertions/card-index-organizes-knowledge-as-addressable-linked-notes]]"
  - "[[30_assertions/critical-apparatus-binds-reading-to-witnesses]]"
  - "[[30_assertions/prov-validity-is-internal-consistency]]"
  - "[[30_assertions/llm-summaries-broaden-the-scope-of-findings]]"
  - "[[30_assertions/layer-model-assigns-each-layer-its-anchor-form]]"
  - "[[30_assertions/anchors-are-minted-at-their-own-layer-and-bind-one-layer-down]]"
  - "[[30_assertions/source-type-follows-storability-and-fixes-the-anchor-form]]"
  - "[[30_assertions/output-binds-load-bearing-sentences-by-footnote-and-marks-posits]]"
  - "[[30_assertions/first-review-pass-concentrates-at-the-distillate-layer]]"
  - "[[30_assertions/modality-drift-is-the-most-frequent-recorded-defect]]"
  - "[[30_assertions/no-recorded-verdict-was-contradicts-or-not-in-the-text]]"
posits: 2
created: 2026-08-10
updated: 2026-08-10
---

# Die Stützungslücke

Eine Quellenangabe, die auflöst, ist noch kein Beleg. In einem Audit generativer Suchmaschinen stützten nur 74,5 Prozent der Zitate den Satz, an dem sie hängen, und nur 51,5 Prozent der Sätze waren vollständig durch ihre Zitate gedeckt.[^1] Erfundene Referenzen sind messbar verbreitet, 55 Prozent der Werke, die GPT-3.5 in generierten Papers zitierte, existierten nicht, bei GPT-4 waren es 18 Prozent, und drei kommerzielle juristische Recherchewerkzeuge halluzinieren in 17 bis 33 Prozent der Fälle, eine Rate, die ihre Studie als gegenüber GPT-4 reduziert berichtet.[^2] Der schwerer zu entdeckende Fall ist der andere. Eine Antwort zitiert reale Dokumente und belegt trotzdem falsch, weil das Zitat seine Quelle fehlinterpretiert oder eine unpassende nennt. Wer das finden will, muss die zitierten Texte öffnen, lesen, ihre Autorität einschätzen und sie mit der Behauptung vergleichen.[^3]

Die NLP-Forschung behandelt die Zuordnungsfrage als eigene Größe. Attribution meint den akkuraten Gebrauch von Quelldokumenten zur Stützung generierten Texts, geprüft gegen die mitgelieferte Quelle und ausdrücklich ohne absolutes Urteil über die Faktizität der Aussage.[^4] Eine Trennung ähnlicher Bauart kennt die historische Methodenlehre aus ihren klassischen Handbüchern, die Prüfung der Überlieferung und der Herkunft einer Quelle geht der Prüfung ihrer Glaubwürdigkeit voraus, und beide sind eigene Arbeitsschritte.[^5] Beide Trennungen halten die Zuordnung einer Aussage zu ihrer Quelle von der Bewertung dieser Aussage getrennt.[^13]

Der Grounded Vault ist unser Versuch, diese Zuordnung als Struktur anzulegen. Die Architektur läuft über fünf Schichten, und jede trägt ihre eigene Ankerform, von der unangetasteten Quelle über die Markdown-Repräsentation mit ihren Blockankern und das Destillat mit seinen Aussagen-IDs bis zur Assertion und zum Fußnotenanker des fertigen Texts.[^12] Zwei Regeln halten diese Kette zusammen, Anker entstehen nur auf der Schicht, zu der sie gehören, und jede Schicht verweist ausschließlich auf die direkt darunterliegende.[^14] Welche Ankerform eine Quelle erlaubt, entscheidet sich daran, ob ihr Inhalt im Vault gespeichert werden darf; ein speicherbarer Volltext wird über Blockreferenzen adressiert, eine nur zitierbare Publikation über das wörtliche Zitat mit Fundstelle, ein Datensatz über eine reproduzierbare Berechnung.[^15] Die tragenden Sätze des fertigen Texts verweisen per Fußnote auf Assertions, jede eigene Schlussfolgerung wird als Posit markiert, so wie es dieser Beitrag tut.[^16]

Neu ist an dieser Anlage weniger, als es scheint. Das Destillat ist das Exzerpt der geisteswissenschaftlichen Arbeitspraxis, eine Quelle, ausgewählte Aussagen, jede mit Fundstelle. Die Assertion-Schicht arbeitet wie Luhmanns Zettelkasten, dessen Karten über feste Nummern adressierbar sind und dessen Funktionieren an einer dichten Verweisstruktur zwischen ihnen hängt, eine unverlinkte Notiz geht dort unwiederbringlich verloren.[^6] Der Fußnotenvertrag des Endtexts folgt dem kritischen Apparat, wie ihn die TEI kodiert, jede Lesart wird über ein Attribut mit den Zeugen verknüpft, die sie bezeugen, und die Guidelines empfehlen für jeden Zeugen eine eindeutige Sigle und in der Regel ein Zeugenregister im Editionskopf.[^7] Die Methode setzt diese Praktiken unter agentische Bedingungen fort. Agenten führen die Arbeitsschritte aus, und Maschinen prüfen die Struktur.

Die Architektur unterscheidet dabei zwei Dinge, die leicht verschwimmen. Grounding ist die strukturelle Rückbindung, ein Anker, der auflöst. Ob die Fundstelle die Aussage trägt, ist eine eigene Prüfentscheidung, und ob die Aussage wahr ist, noch einmal eine andere. Das W3C-Provenienzmodell zieht dieselbe Grenze für sich selbst, die Validität eines Provenienz-Records ist dort interne Konsistenz, eine kohärente Historie, und Provenienz gilt als Grundlage für Vertrauensentscheidungen.[^8] Deshalb prüfen im Grounded Vault drei getrennte Instanzen. Die deterministische Validierung prüft Form und Auflösbarkeit der Anker. Ein adversariales LLM-Review prüft je Paar aus Aussage und Fundstelle, ob die Fundstelle trägt, mit fünf festen Verdikten, von denen nur die volle Stützung besteht. Die menschliche Verifikation entscheidet zuletzt, ob die vorgelegte Fundstelle als Evidenz akzeptiert wird, und nur sie darf den höchsten Status setzen.

Dass die maschinelle Prüfung nötig ist, zeigt schon der Aufbau dieses Bestands. LLM-Zusammenfassungen wissenschaftlicher Texte verbreitern den Geltungsbereich der Originalbefunde systematisch, und die Instruktion, Ungenauigkeiten zu vermeiden, verdoppelt diese Übergeneralisierung nahezu.[^9] Der erste Prüfdurchgang über diesen Bestand meldete Verdikte für 501 Paare aus Aussage und Fundstelle, verteilt über 46 Dokumente, mit vier Fünfteln davon auf der Destillat-Ebene.[^10] Erfasst wurden dabei 101 Verdikte unterhalb voller Stützung, und unter den erfassten Mängeln ist die Modalitätsdrift mit 32 Fällen die häufigste Kategorie, vor dem verfehlten Geltungsbereich mit 19, dem Griff in den Nachbarblock mit 18 und dem unverankerten Detail mit 17.[^17] Kein erfasstes Verdikt lautete contradicts oder not in the text.[^18] Jeder Mangel wurde vor der Publikation zurückgebaut.

Zwei Grenzen gehören in den Auftakt. Ein auflösbarer Anker garantiert Rückverfolgbarkeit. Über die Wahrheit der Quelle und die Qualität des fertigen Texts sagt er nichts, und ob die Methode die inhaltliche Qualität gegenüber unverankertem Schreiben hebt, wissen wir nicht.[^11] Die Provenienztiefe entsteht zudem nur, wenn die Quellen zum Verarbeitungszeitpunkt archiviert werden, nachträglich lässt sie sich kaum herstellen. Der zugrunde liegende Bestand ist öffentlich, und jede Fußnote dieses Texts löst in ihm auf. Die folgenden Beiträge entwickeln die Begriffe, die Prüfregeln, den realen Aufbau dieses Vaults und seine Werkzeuge.

[^1]: Grounded in [[30_assertions/generated-citations-often-fail-to-support-their-sentences]].
[^2]: Grounded in [[30_assertions/source-binding-lowers-unsupported-citation-without-eliminating-it]].
[^3]: Grounded in [[30_assertions/resolvable-citation-without-support-is-a-distinct-error-class]].
[^4]: Grounded in [[30_assertions/attribution-is-separate-from-correctness]].
[^5]: Grounded in [[30_assertions/historical-method-separates-origin-check-from-credibility]].
[^6]: Grounded in [[30_assertions/card-index-organizes-knowledge-as-addressable-linked-notes]].
[^7]: Grounded in [[30_assertions/critical-apparatus-binds-reading-to-witnesses]].
[^8]: Grounded in [[30_assertions/prov-validity-is-internal-consistency]].
[^9]: Grounded in [[30_assertions/llm-summaries-broaden-the-scope-of-findings]].
[^10]: Grounded in [[30_assertions/first-review-pass-concentrates-at-the-distillate-layer]].
[^11]: Posit: eigene Einschätzung, ein kontrollierter Vergleich mit unverankert geschriebenen Texten ist uns nicht bekannt. Open evidence question: Gibt es einen solchen Vergleich, und wie wäre er anzulegen?
[^12]: Grounded in [[30_assertions/layer-model-assigns-each-layer-its-anchor-form]].
[^13]: Posit: eigene Zusammenschau von [^4] und [^5]. Keine der beiden Quellen stellt diesen Vergleich selbst an. Open evidence question: Gibt es wissenschaftsgeschichtliche Literatur, die die quellenkritische Zweistufigkeit und die Attributionsforschung aufeinander bezieht?
[^14]: Grounded in [[30_assertions/anchors-are-minted-at-their-own-layer-and-bind-one-layer-down]].
[^15]: Grounded in [[30_assertions/source-type-follows-storability-and-fixes-the-anchor-form]].
[^16]: Grounded in [[30_assertions/output-binds-load-bearing-sentences-by-footnote-and-marks-posits]].
[^17]: Grounded in [[30_assertions/modality-drift-is-the-most-frequent-recorded-defect]].
[^18]: Grounded in [[30_assertions/no-recorded-verdict-was-contradicts-or-not-in-the-text]].

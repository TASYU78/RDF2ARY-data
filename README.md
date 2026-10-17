# RDF2ARY-data

Research data accompanying **Unified Semantic Storage and Graph Construction
for Multimodal Annotations: A Case Study of Classical Chinese Poetry**.

**Authors:** Yanjie Huang and Tao Chen.  
**Correspondence:** chent283@mail.sysu.edu.cn  
**Dataset version:** 1.0.0

This dataset records the 22-annotation *Baima Pian* case used to examine
normalization, RDF storage, canonical-record reconstruction, cross-modal
queries and downstream exports. It contains research data and declarative
schemas and queries. The RDF2ARY application implementation is not included.

## Data and documentation

| Directory or file | Contents |
|---|---|
| [raw-exports](raw-exports) | Five Label Studio/Voyager annotation exports, with media references but no media binaries |
| [mappings](mappings) | Platform field, semantic, resource and locator mappings |
| [expected](expected) | Expected records and query answers, with the timing of their preparation documented |
| [outputs/full-canonical-records.json](outputs/full-canonical-records.json) | All 22 canonical annotation records |
| [outputs/case-five-modality.ttl](outputs/case-five-modality.ttl) | The 608-triple base annotation graph |
| [outputs/expression-rebuilt-core.ttl](outputs/expression-rebuilt-core.ttl) | The 606-triple graph rebuilt from the annotation expressions |
| [outputs/case-five-modality-local-links.ttl](outputs/case-five-modality-local-links.ttl) | The 630-triple graph supplemented with local access links |
| [outputs/case-records.nary](outputs/case-records.nary) | Full-precision N-ary expressions and record envelopes |
| [queries](queries) | Three SPARQL queries |
| [schema](schema) | RDF ontology and SHACL constraints |
| [outputs/locator-fixtures](outputs/locator-fixtures) | 23 constructed valid locator graphs |
| [outputs](outputs) | Standard export pages, query results and validation reports |
| [materials/text](materials/text) | Fixed plain-text view and TEI encoding |
| [resource-sources.json](resource-sources.json) | Available bibliographic/source information and unresolved resource metadata |
| [FILE-MANIFEST.csv](FILE-MANIFEST.csv) | File sizes and SHA-256 checksums |

## Checking the reported results

The canonical records comprise 4 text, 5 image, 4 audio, 8 video and 1 3D
annotation. Parse the Turtle files with an RDF tool to check their triple
counts. The two triples outside the rebuilt annotation core are a concept
label and a passage-to-concept relation added outside individual records.

Run the following queries against `outputs/case-five-modality.ttl` with an
RDF 1.1/SPARQL 1.1 tool:

| Query | Expected rows |
|---|---:|
| `queries/line_evidence.rq` | 16 (5, 6 and 5 for the three passages) |
| `queries/concept_evidence.rq` | 6 across 5 resources |
| `queries/annotation_detail.rq` | 1 |

The Web Annotation page contains 17 records and the IIIF image page contains
5 records. Those 5 images also occur in the Web Annotation page. Structured
assertions and canonical snapshots accompany the native selector mappings
as extensions. Locator fixtures are separate from the 22 cultural-case
annotations; `outputs/locator-coverage-report.json` also records the six
invalid-input checks.

Original numerical precision and identifiers are retained. The initial
18 reference interpretations were retrospective; the four supplementary
video-region interpretations preceded conversion. They are not a blinded
independent gold standard.

## Resources and reproduction scope

The original book-page image, audio recording, video recording and 3D model
are not redistributed here. Their references, technical metadata and annotation
locators are provided where available. The text and page image use the cited
1977 Zhonghua Shuju edition of *Wen xuan*, as confirmed by the author. The
video creator/title and model creator/license are not yet fully documented.

The saved HTTP and Mirador reports describe local tests. `localhost` and
`127.0.0.1` URLs are historical service bindings, not public endpoints. This
dataset alone does not provide the original media services or reproduce
media playback and viewing. Some reports retain hashes or paths of other
project artifacts not included here. Rerunning the original platform-adapter
pipeline requires the application implementation, which is not publicly
released. Data, queries and schemas can be inspected independently.

Source annotation identifiers, annotator identifiers and timestamps are
retained to make the recorded provenance comparisons inspectable.

## Citation and versions

See [CITATION.cff](CITATION.cff). Cite a fixed commit or release corresponding
to the manuscript, rather than relying only on the moving `main` branch.
No DOI has been assigned to this GitHub deposit.

## Reuse

No dataset-wide reuse license has been selected. See [RIGHTS.md](RIGHTS.md).
Public availability does not supply a blanket license for linked resources.

## Funding

National Social Science Fund of China (NSSFC), Project No. 23BTQ088:
Research on Knowledge Representation Models and Intelligent Systems for
Multimodal Cultural Heritage Data.

# TF-TF Knowledge Graph Serializations
| Network | Nodes | Edges | Assertions | Size | Date Updated |
| :--------- | :--------- | :--------- | :--------- | :--------- | :--------- |
| Node Weighted | 1,554 | 130,793 | [download] | 2.3 MiB | 11-12-24 |
| Signature Shuffling | 1,555 | 108,715 | [download] | 2.1 MiB | 11-12-24 |
| Edge Weighted | 1,546 | 53,003 | [download] | 854.6 KiB | 11-12-24 |
| Unfiltered | 1,556 | 372,382 | [download] | 1.7 MiB | 11-12-24 |

## Raw Data
## Benchmarking Libraries
| Source | Library Name | Size | Date Updated |
| :--------- | :--------- | :--------- | :--------- |
| ChEA3 Primary Libraries | [ARCHS4_Coexpression](https://maayanlab.cloud/chea3/assets/tflibs/ARCHS4_Coexpression.gmt) | 3.2 MB | 11-12-24 |
|| [ENCODE_ChIP-seq](https://maayanlab.cloud/chea3/assets/tflibs/ENCODE_ChIP-seq.gmt) | 5.6 MB | 11-12-24 |
|| [Enrichr_Queries](https://maayanlab.cloud/chea3/assets/tflibs/Enrichr_Queries.gmt) | 2.5 MB | 11-12-24 |
|| [GTEx_Coexpression](https://maayanlab.cloud/chea3/assets/tflibs/GTEx_Coexpression.gmt) | 3.2 MB | 11-12-24 |
|| [Literature_ChIP-seq](https://maayanlab.cloud/chea3/assets/tflibs/Literature_ChIP-seq.gmt) | 2.5 MB | 11-12-24 |
|| [ReMap_ChIP-seq](https://maayanlab.cloud/chea3/assets/tflibs/ReMap_ChIP-seq.gmt) | 3.0 MB | 11-12-24 |
| Enrichr | [TRRUST_Transcription_Factors_2019](https://maayanlab.cloud/Enrichr/geneSetLibrary?mode=text&libraryName=TRRUST_Transcription_Factors_2019) | 80 KB | 11-12-24 |
|| [TRANSFAC_and_JASPAR_PWMs](https://maayanlab.cloud/Enrichr/geneSetLibrary?mode=text&libraryName=TRANSFAC_and_JASPAR_PWMs) | 2.8 MB | 11-12-24 |

## RummaGEO 
| Source | Size | Date Updated |
| :--------- | :--------- | :--------- |
| [RummaGEO Human Gene Sets](https://s3.amazonaws.com/maayanlab-public/rummageo/2.5/human-geo-auto.gmt.gz) | 1.1 GB | 11-4-24 |
| [Control vs. Perturbation Gene Sets](https://minio.dev.maayanlab.cloud/hgrn-chear/single_perturbation_gses.txt) | 126.9 KiB | 11-12-24 |

# Network Building Notebooks
| File | Size | Date Updated | Description |
| :--------- | :--------- | :--------- | :--------- |
| [construct_edge_list.ipynb](https://github.com/MaayanLab/TranscriptionNetwork-Demo/blob/main/tf_knowledge_graph/construct_edge_list.ipynb) | 18.3 KB | 11-5-24 | Build the unfiltered network edge list using RummaGEO and ChEA3 |
| [filter_network_assertions.ipynb](https://github.com/MaayanLab/TranscriptionNetwork-Demo/blob/main/tf_knowledge_graph/filter_network_assertions.ipynb) | 20.8 KB | 11-5-24 | Filter the network assertions on significance using three methods of expected counts: signature shuffling, node weighted, and edge weighted |
| [benchmark_network.ipynb](https://github.com/MaayanLab/TranscriptionNetwork-Demo/blob/main/tf_knowledge_graph/benchmark_network.ipynb) | 12.8 KB | 11-5-24 | Benchmark the filtered networks against TF interaction libraries from ChEA3 and Enrichr |
| [format_assertions_for_ingestion.ipynb](https://github.com/MaayanLab/TranscriptionNetwork-Demo/blob/main/tf_knowledge_graph/format_assertions_for_ingestion.ipynb) | 14.6 KB | 11-12-24 | Format the assertions for ingestion into Neo4j |



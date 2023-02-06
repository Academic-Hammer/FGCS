# FGCS

## Introduction

FGCS is a dataset constructed for entity-relation extraction in computer science field. The proposed dataset includes 1,948 sentences of 6 entity types with up to 9 layers of nesting and 5 relation types. 

## Data format

The dataset is divided into train set (70%), validation set (10%), test set (20%).

| train | dev | test |
| :-: | :-: | :-: |
| 1364 | 195 | 389 |

Each instance in the dataset is organized as follow:

```
{
  "tokens": ["We", "start", "from", "analyzing", "the", "procedures", ...],
  "ners": [
    [16, 16, "Metric"], 
    [13, 13, 16, 16, "Metric"],
    ...
  ],
  "relations": [
    [0, 1, "Hyponym-of"],
    ...
  ],
  "discontinuous": true
}
```

Entries in ners are organized as ```[token_start, token_end, type]``` for general entities while ```[first_span_start, first_span_end, second_span_start, second_span_end, type]``` for discontinuous entities.

Entries in relations are organized as ```[head_entity_index, tail_entity_index, type]```.

```discontinuous``` indicated whether there is a discontinuous entity in this sentence.

## Specification

The proposed dataset contains three types of fine-grained entities: **nested entities**, **discontinuous entities** and **Minimal Independent Semantics (MIS) entities**. The statistic of entities and relations is following:

|  | Entities | Relations | Nested Entities | Discontinuous Entities | MIS Entities | 
| :-: | :-: | :-: | :-: | :-: | :-: | 
| count | 8,559 | 5,903 | 3,084 | 120 | 652 |
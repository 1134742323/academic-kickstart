---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "MagniﬁerNet: TowardsSemanticRegularizationandFusionforPerson Re-identiﬁcation"
authors: [Yushi Lan, Yuan Liu, Maoqing Tian, Hongsheng Li, et al.]
date: 2019-12-13T18:50:02+08:00
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2019-12-13T18:50:02+08:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: "MagnifierNet"
publication_short: ""

abstract: "Although person re-identification (ReID) has achieved significant improvement recently by enforcing part alignment, it is still a challenging task when it comes to distinguishing visually similar identities or identifying occluded person.
Although person re-identification (ReID) has achieved significant improvement recently by enforcing part alignment, it is still a challenging task when it comes to distinguishing visually similar identities or identifying occluded person. In these scenarios, magnifying details in each part features and selectively fusing them together may provide a feasible solution. 
In this paper, we propose MagnifierNet, a novel network which accurately mines details for each semantic region and selectively fuse all semantic feature representations. Apart from conventional global branch, our proposed network is composed of a Semantic Regularization Branch (SRB) as learning regularizer and a Semantic Fusion Branch (SFB) towards selectively semantic fusion. The SRB learns with limited number of semantic regions randomly sampled in each batch, which forces the network to learn detailed representation for each semantic region, and the SFB selectively fuses semantic region information in a sequential manner, focusing on beneficial information while neglecting irrelevant features or noises. 
Although person re-identification (ReID) has achieved significant improvement recently by enforcing part alignment, it is still a challenging task when it comes to distinguishing visually similar identities or identifying occluded person. In these scenarios, magnifying details in each part features and selectively fusing them together may provide a feasible solution. 
"

# Summary. An optional shortened abstract.
summary: ""

tags: [Deep Learning, Neural Network]
categories: [ComputerVision, Deep Learning, ReID]
featured: true

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_pdf:
url_code:
url_dataset: https://www.ee.cuhk.edu.hk/~xgwang/CUHK_identification.html
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Our method is able to discover tiny differences of semantic regions"
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

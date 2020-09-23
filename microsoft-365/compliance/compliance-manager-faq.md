---
title: Microsoft コンプライアンスマネージャーの FAQ
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーに関してよく寄せられる質問への回答を検索します。これにより、組織はリスク評価を簡略化および自動化できます。
ms.openlocfilehash: 3e1b6cdbcafd0cb4af4545cb258dab2ce082a2d8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204449"
---
# <a name="compliance-manager-frequently-asked-questions"></a>コンプライアンスマネージャーのよく寄せられる質問

## <a name="is-compliance-manager-and-compliance-score-the-same-thing-or-are-they-different"></a>コンプライアンスマネージャーとコンプライアンススコアが同じかどうか、または相違点

コンプライアンスマネージャーは、1つのソリューションだけで済みます。 このセクションでは、以下の基本的な概要から始まる移行手順について説明します。 また、次のセクションのいずれかに直接移動すると役立つ場合があります。

- [組織は、Microsoft Service Trust Portal にあるコンプライアンスマネージャー (クラシック版またはパブリックプレビュー版) を主に使用していました。](#your-organization-regularly-used-compliance-manger-in-the-service-trust-portal)

- [お客様の組織では、Microsoft 365 コンプライアンスセンターにある、主にコンプライアンススコア (パブリックプレビュー) を使用していました。](#your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center)

- [組織はコンプライアンスマネージャーを初めて使用する](#youre-new-to-compliance-manager
)
#### <a name="the-basics"></a>基本事項

Microsoft コンプライアンスマネージャーは、Microsoft Service Trust Portal の内部でコンプライアンス管理ソリューションとして開始されました。  コンプライアンスソリューションが Microsoft 365 コンプライアンスセンターに含まれている場合、この場所に対してよりユーザーフレンドリな設計を使用して、新しい経験を開発しました。 コンプライアンススコアパブリックプレビューは、Microsoft 365 コンプライアンスセンター (2019 年11月) でリリースされました。 コンプライアンススコアコンプライアンスマネージャーと同じバックエンドを共有し、お客様が両方の場所で作業できるようにします。 2019年11月以降、新機能を構築し、お客様からのフィードバックに応答したため、いくつかの更新プログラムをリリースしました。

Microsoft 365 コンプライアンスセンター (年 9 2020 月) のコンプライアンスマネージャーの一般的な可用性は、この進化を完了します。 コンプライアンスマネージャーは、統合されたエンドツーエンドのコンプライアンスソリューションです。 コンプライアンスのスコアは、コンプライアンスマネージャーの重要なコンポーネントとして残ります。

コンプライアンスマネージャーの GA リリースの新機能の詳細については、この [ブログ投稿](https://aka.ms/compliancemanager/GAblog) をお読みください。

#### <a name="your-organization-regularly-used-compliance-manger-in-the-service-trust-portal"></a>組織がサービス信頼ポータルで定期的にコンプライアンスマネージャーを使用している

Service Trust Portal でコンプライアンスマネージャーを使用していた場合、組織のすべてのデータは、Microsoft 365 コンプライアンスセンターのコンプライアンスマネージャーに現在存在して https://compliance.microsoft.com/compliancemanager います。 コンプライアンスマネージャーが新しい場所で作業を再開するために必要な操作はありません。以前の場所にあるブックマークを更新する方法はありません。 評価とその他のデータはすべてお客様に提供されています。

コンプライアンスマネージャー (プレビュー) は、サービス信頼ポータルからはアクセスできなくなります。また、すべてのリンクが Microsoft 365 コンプライアンスセンターの新しい場所にリダイレクトされることに注意してください。 コンプライアンスマネージャー (クラシック) はサービス信頼ポータルに残りますが、使用は推奨されません。

以前のバージョンのコンプライアンスマネージャーで使用したもの (アクションの完了 ("改善アクション" と呼ばれました)、評価の作成など、新しいコンプライアンスマネージャーで行うことができます。 150を超える新しい評価テンプレートを追加し、テンプレートの作成プロセスを改善しました。 今後のリリースでさらに強化された機能を追加します。

役に立つリソースを以下に示します。

- [新しいコンプライアンスマネージャーの経験を理解する](compliance-manager-setup.md#understand-the-compliance-manger-dashboard)
- [新しいホームでコンプライアンスマネージャーのアクセス許可とその他のセットアップ情報を検索する](compliance-manager-setup.md#who-can-access-compliance-manager)
- [Microsoft 365 コンプライアンスセンターの詳細情報](microsoft-365-compliance-center.md)

#### <a name="your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center"></a>組織が Microsoft 365 コンプライアンスセンターでコンプライアンススコア (パブリックプレビュー) を使用した

パブリックプレビューでコンプライアンススコアを使用した場合は、コンプライアンスマネージャーがほぼ同じように表示されることがわかります。ダッシュボードでスコアが目立つようになっています。 GA リリースでは、評価のためのテンプレートの作成や変更など、特定の評価管理機能を実行するために Microsoft 365 コンプライアンスセンターを終了する必要がなくなりました。 すべての機能が1つの場所に配置されるようになりました。 コンプライアンススコアのプレビューバージョンに含まれていたデータは、コンプライアンスマネージャーの GA バージョンに保持されます。

コンプライアンススコアダッシュボードビューをフィルター処理した場合、このフィルターは、9月に新しいコンプライアンスマネージャーを展開したときにリセットされたことに注意してください。 必要なフィルターを再適用する必要があります。

コンプライアンスマネージャーにも新しいライセンス条項があります。 ライセンスについては、以下の質問を参照してください。

#### <a name="youre-new-to-compliance-manager"></a>コンプライアンスマネージャーの使用が初めての方

コンプライアンスマネージャーは、コンプライアンス活動を管理および追跡するための、Microsoft 365 コンプライアンスセンターのエンドツーエンドのソリューションです。 初めてアクセスしたときに、コンプライアンスの状況を最初に評価することになるため、コンプライアンスへの移行を開始するのに最適な場所です。 詳細な学習を開始するための適切な場所は次のとおりです。

- [コンプライアンスマネージャーの概要を取得する](compliance-manager.md)
- [クイックスタートガイドを使用して段階的に向上させる](compliance-manager-quickstart.md)
- [Microsoft 365 コンプライアンスセンターの詳細情報](microsoft-365-compliance-center.md)

## <a name="are-there-licensing-requirements-for-using-compliance-manager"></a>コンプライアンスマネージャーを使用するためのライセンス要件はありますか。

はい。 コンプライアンスマネージャーの GA リリースには、新しいライセンス条項が含まれています。 Office 365 と Microsoft 365 のライセンスを持つすべての組織 (米国政府および DoD を除く) は、コンプライアンスマネージャーにアクセスできます。 ただし、組織で使用可能な評価と評価テンプレートの管理方法は、使用許諾契約によって異なります。 詳細については、「 [Microsoft 365 ライセンスガイダンス」の「セキュリティとコンプライアンス」を](https://go.microsoft.com/fwlink/?linkid=2132371) 参照してください。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>スコアが高い場合は、完全に準拠していることを意味します。

いいえ。 コンプライアンススコアは、データ保護と規制基準に関するリスクを軽減するために、推奨されるアクションを完了するための進捗状況を測定します。 特定の標準または規制に関して、組織のコンプライアンスの絶対的な測定基準を表すものではありません。 コンプライアンスマネージャーおよびコンプライアンススコアは、何らかの保証として解釈されることはありません。

## <a name="can-i-use-compliance-manager-for-non-microsoft-products"></a>Microsoft 以外の製品でコンプライアンスマネージャーを使用できますか。

コンプライアンスマネージャーは、継続的な監視および推奨されるアクションを Microsoft クラウドサービスに対してのみ提供しますが、サードパーティのサービスのコンプライアンスマネージャーでカスタム評価を追加することができます。 この方法では、Microsoft コンプライアンスマネージャーを SaaS コンプライアンス管理ツールとして使用して、デジタルアセット全体のコントロールを管理することができます。
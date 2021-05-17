---
title: Microsoft コンプライアンス マネージャーに関するよく寄せられる質問
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
description: Microsoft コンプライアンス マネージャーに関してよく寄せられる質問に対する回答を見つけ、組織がリスク評価を簡素化および自動化するのに役立ちます。
ms.openlocfilehash: efa9de8506c088ceae64de26d32efe8553d0b574
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570396"
---
# <a name="compliance-manager-frequently-asked-questions"></a>コンプライアンス マネージャーに関するよく寄せられる質問

## <a name="is-compliance-manager-and-compliance-score-the-same-thing-or-are-they-different"></a>コンプライアンス マネージャーとコンプライアンス スコアは同じか、それとも異なっていますか?

これで、コンプライアンス マネージャーというソリューションが 1 つだけになります。 このセクションでは、以下の基本的な概要から移行について説明します。 また、次のいずれかのセクションに直接ジャンプすると便利な場合があります。

- [組織は主に、Microsoft Service Trust Portal にあるコンプライアンス マネージャー (クラシック バージョンまたはパブリック プレビュー バージョン) を使用しました。](#your-organization-regularly-used-compliance-manager-in-the-service-trust-portal)

- [組織は、コンプライアンス センターにあるコンプライアンス スコア (パブリック プレビュー) を主にMicrosoft 365使用しました。](#your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center)

- [コンプライアンス マネージャーの組織が新しい](#youre-new-to-compliance-manager
)
#### <a name="the-basics"></a>基本事項

Microsoft コンプライアンス マネージャーは、Microsoft Service Trust Portal 内のコンプライアンス管理ソリューションとして始まりました。  コンプライアンス ソリューションがコンプライアンス センターにMicrosoft 365、この場所のユーザーフレンドリーなデザインで新しいエクスペリエンスを開発しました。 コンプライアンス スコアのパブリック プレビューは、2019 年 11 月Microsoft 365コンプライアンス センターでリリースされました。 コンプライアンス スコアは、コンプライアンス マネージャーと同じバックエンドを共有し、ユーザーが両方の場所で作業できるようにしました。 2019 年 11 月以降、新しい機能を構築し、お客様からのフィードバックに対応する中で、いくつかの更新プログラムがリリースされました。

2020 年 9 月のコンプライアンス Microsoft 365コンプライアンス マネージャーの一般提供は、この進化を完了します。 コンプライアンス マネージャーは、統合されたエンドツーエンドのコンプライアンス ソリューションです。 コンプライアンス スコアは、コンプライアンス マネージャーの重要なコンポーネントです。

コンプライアンス マネージャー [の GA](https://aka.ms/compliancemanager/GAblog) リリースの新機能の詳細については、このブログ記事をご覧ください。

#### <a name="your-organization-regularly-used-compliance-manager-in-the-service-trust-portal"></a>組織は、サービス信頼ポータルでコンプライアンス マネージャーを定期的に使用しました

サービス信頼ポータルでコンプライアンス マネージャーを使用した場合、組織のすべてのデータは、コンプライアンス センターのコンプライアンス Microsoft 365に存在します https://compliance.microsoft.com/compliancemanager 。 コンプライアンス マネージャーの作業を新しい場所で再開するには、以前の場所に必要なブックマークを更新する以外に必要な操作は何もありません。 すべての評価と他のデータが引き継がれ、

コンプライアンス マネージャー (プレビュー Microsoft 365) はサービス信頼ポータルでアクセスできなくなったので、コンプライアンス センター内の新しい場所にリダイレクトされます。 コンプライアンス マネージャー (クラシック) はサービス信頼ポータルに残りますが、使用は推奨されません。

以前のバージョンのコンプライアンス マネージャーでは、アクションの完了 (現在は "改善アクション" と呼ばれる) や評価の作成など、以前のバージョンで行ったすべての操作を、新しいコンプライアンス マネージャーで実行できます。 150 を超える新しい評価テンプレートが追加され、テンプレートの作成プロセスが改善されました。 今後のリリースでは、さらに機能強化が追加されます。

以下に役立つリソースを示します。

- [コンプライアンス マネージャーの新しいエクスペリエンスを理解する](compliance-manager-setup.md#understand-the-compliance-manager-dashboard)
- [新しいホームでコンプライアンス マネージャーのアクセス許可とその他のセットアップ情報を検索する](compliance-manager-setup.md#who-can-access-compliance-manager)
- [コンプライアンス センターの詳細Microsoft 365する](microsoft-365-compliance-center.md)

#### <a name="your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center"></a>組織は、コンプライアンス センターでコンプライアンス スコア (パブリック プレビュー) Microsoft 365使用しました

パブリック プレビューでコンプライアンス スコアを使用した場合は、コンプライアンス マネージャーの外観が大きく同じで、ダッシュボードでスコアが目立つように表示されます。 GA リリースでは、評価用テンプレートの作成や変更など、特定の評価管理機能を実行するために、Microsoft 365 コンプライアンス センターを離れる必要がなくなりました。 すべての機能が 1 か所に存在します。 プレビュー バージョンのコンプライアンス スコアに含めたデータは、GA バージョンのコンプライアンス マネージャーに残ります。

コンプライアンス スコア ダッシュボード ビューをフィルター処理した場合、これらのフィルターは 9 月に新しいコンプライアンス マネージャーを展開した際にリセットされた点に注意してください。 フィルターを再適用する必要があります。

コンプライアンス マネージャーには、新しいライセンス条項があります。 ライセンスに関する以下の質問を参照してください。

#### <a name="youre-new-to-compliance-manager"></a>コンプライアンス マネージャーの新機能

コンプライアンス マネージャーは、コンプライアンス アクティビティの管理と追跡を行Microsoft 365コンプライアンス センターのエンドツーエンド ソリューションです。 初めてアクセスした場合にコンプライアンス体制の初期評価を行うので、コンプライアンスの取り組み開始に最適な場所です。 以下は、学習を始めるのに良い場所です。

- [コンプライアンス マネージャーの概要を確認する](compliance-manager.md)
- [クイック スタート ガイドを使用して、ステージの立ち上がりを支援する](compliance-manager-quickstart.md)
- [コンプライアンス センターの詳細Microsoft 365する](microsoft-365-compliance-center.md)

## <a name="are-there-licensing-requirements-for-using-compliance-manager"></a>コンプライアンス マネージャーを使用する場合のライセンス要件はありますか?

はい。 コンプライアンス マネージャーの GA リリースには、新しいライセンス条項が含まれている。 Office 365 および Microsoft 365 ライセンスを持つすべての組織、および米国政府機関 Community (GCC) モデレート、GCC High、および国防総省 (DoD) のお客様は、コンプライアンス マネージャーにアクセスできます。 ただし、組織で利用できる評価と評価テンプレートの管理方法は、ライセンス契約によって異なります。 詳細については[、「Microsoft 365のライセンス ガイダンス」を](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>スコアが高い場合は、完全に準拠しているという意味ですか?

いいえ。 コンプライアンス スコアは、データ保護と規制基準に関するリスクを軽減するために役立つ推奨アクションの完了状況を測定します。 これは、特定の標準または規制に関する組織のコンプライアンスの絶対的な尺度を表すのではありません。 コンプライアンス マネージャーとコンプライアンス スコアは、いかなる方法でも保証として解釈される必要はありません。

## <a name="can-i-use-compliance-manager-for-non-microsoft-products"></a>Microsoft 以外の製品にコンプライアンス マネージャーを使用できますか?

コンプライアンス マネージャーは、Microsoft クラウド サービスに対する継続的な監視と推奨されるアクションのみを提供しますが、サードパーティ サービスのコンプライアンス マネージャーでカスタム評価を追加できます。 この方法で、Microsoft Compliance Manager を SaaS コンプライアンス管理ツールとして使用して、デジタル資産全体のすべてのコントロールを管理できます。

## <a name="whats-happening-to-compliance-manager-classic-in-the-service-trust-portal"></a>サービス信頼ポータルのコンプライアンス マネージャー (クラシック) に何が起こっていますか?

Microsoft Service Trust Portal に存在する従来のバージョンのコンプライアンス マネージャーは、まもなく廃止されます。 メッセージ Microsoft 365通知は、コンプライアンス マネージャー (クラシック) の最終退職日の少なくとも 60 日前に表示されます。 コンプライアンス マネージャー (クラシック) でコンプライアンス 活動を管理しているお客様は、評価やコントロールなどのデータを、Microsoft 365 コンプライアンス センターの新しいコンプライアンス マネージャー ソリューションに移動する必要があります。 コンプライアンス マネージャー (クラシック) が廃止された場合、顧客データはコンプライアンス センター Microsoft 365コンプライアンス マネージャーに自動的に転送されません。

新しいコンプライアンス マネージャーをすばやくセットアップする方法については、コンプライアンス マネージャーの [クイック スタート ガイドを参照](compliance-manager-quickstart.md) してください。
---
title: Microsoft コンプライアンス マネージャーに関する FAQ
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
description: Microsoft コンプライアンス マネージャーに関してよく寄せられる質問に対する回答を示します。これは、組織がリスク評価を簡素化および自動化するのに役立ちます。
ms.openlocfilehash: 43ecafdfe54b2baec82363ea690a5a820e031232
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050371"
---
# <a name="compliance-manager-frequently-asked-questions"></a>コンプライアンス マネージャーについてよく寄せられる質問

## <a name="is-compliance-manager-and-compliance-score-the-same-thing-or-are-they-different"></a>コンプライアンス マネージャーとコンプライアンス スコアは同じか、それとも異なるのか。

コンプライアンス マネージャーというソリューションが 1 つだけになります。 このセクションでは、以下の基本的な概要から始め、移行について説明します。 また、次のいずれかのセクションに直接移動すると便利な場合があります。

- [組織は主に、Microsoft Service Trust Portal にあるコンプライアンス マネージャー (クラシック バージョンまたはパブリック プレビュー バージョン) を使用しました。](#your-organization-regularly-used-compliance-manager-in-the-service-trust-portal)

- [組織は主に、Microsoft 365 コンプライアンス センターにあるコンプライアンス スコア (パブリック プレビュー) を使用しました。](#your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center)

- [コンプライアンス マネージャーを使用する組織](#youre-new-to-compliance-manager
)
#### <a name="the-basics"></a>基本事項

Microsoft コンプライアンス マネージャーは、Microsoft Service Trust Portal 内のコンプライアンス管理ソリューションとして開始しました。  コンプライアンス ソリューションが Microsoft 365 コンプライアンス センターに入ってきたので、この場所向けのよりユーザー フレンドリーな設計で新しいエクスペリエンスを開発しました。 コンプライアンス スコアパブリック プレビューは、2019 年 11 月に Microsoft 365 コンプライアンス センターでリリースされました。 コンプライアンス スコアはコンプライアンス マネージャーと同じバックエンドを共有し、ユーザーは両方の場所で作業できます。 2019 年 11 月以降、新しい機能を構築し、お客様からのフィードバックに対応する中で、いくつかの更新プログラムがリリースされました。

2020 年 9 月の Microsoft 365 コンプライアンス センターでのコンプライアンス マネージャーの一般提供は、この進化を完了します。 コンプライアンス マネージャーは、統一されたエンドツーエンドのコンプライアンス ソリューションです。 コンプライアンス スコアは、コンプライアンス マネージャーの主要なコンポーネントです。

コンプライアンス マネージャー [の GA](https://aka.ms/compliancemanager/GAblog) リリースの新機能について詳しくは、このブログ記事をご覧ください。

#### <a name="your-organization-regularly-used-compliance-manager-in-the-service-trust-portal"></a>組織が Service Trust Portal でコンプライアンス マネージャーを定期的に使用している

Service Trust Portal でコンプライアンス マネージャーを使用した場合、組織のすべてのデータが Microsoft 365 コンプライアンス センターのコンプライアンス マネージャーに存在します https://compliance.microsoft.com/compliancemanager 。 コンプライアンス マネージャーの作業を新しい場所で再開するために必要な作業は、以前の場所に必要なブックマークを更新する以外に必要な作業は何もありません。 すべての評価と他のデータが持ち越されています。

コンプライアンス マネージャー (プレビュー) は Service Trust Portal でアクセスできなくなったので、コンプライアンス マネージャーへのすべてのリンクから Microsoft 365 コンプライアンス センターの新しい場所にリダイレクトされます。 コンプライアンス マネージャー (クラシック) は Service Trust Portal に残りますが、使用は推奨されません。

アクションの完了 ("改善アクション" と呼ばれる) や評価の作成など、以前のバージョンのコンプライアンス マネージャーで行ったことはすべて、新しいコンプライアンス マネージャーで実行できます。 150 を超える新しい評価テンプレートが追加され、テンプレート作成プロセスが改善されました。 今後のリリースでは、さらに拡張機能が追加されます。

次に役立つリソースを示します。

- [新しいコンプライアンス マネージャーのエクスペリエンスを理解する](compliance-manager-setup.md#understand-the-compliance-manager-dashboard)
- [新しいホームでコンプライアンス マネージャーのアクセス許可とその他のセットアップ情報を検索する](compliance-manager-setup.md#who-can-access-compliance-manager)
- [Microsoft 365 コンプライアンス センターの詳細](microsoft-365-compliance-center.md)

#### <a name="your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center"></a>組織が Microsoft 365 コンプライアンス センターでコンプライアンス スコア (パブリック プレビュー) を使用している

パブリック プレビューでコンプライアンス スコアを使用した場合、コンプライアンス マネージャーの外観は大きく同じで、スコアがダッシュボードで目立つように表示されます。 GA リリースでは、評価用のテンプレートの作成や変更など、特定の評価管理機能を実行するために Microsoft 365 コンプライアンス センターから退出する必要がなくなりました。 すべての機能が 1 か所に存在する。 コンプライアンス スコアのプレビュー バージョンに含めたデータは、GA バージョンのコンプライアンス マネージャーに残ります。

コンプライアンス スコアダッシュボード ビューをフィルター処理した場合、これらのフィルターは 9 月に新しいコンプライアンス マネージャーを展開した際にリセットされた点に注意してください。 使用していたフィルターを再適用する必要があります。

コンプライアンス マネージャーには、新しいライセンス条項も追加されます。 ライセンスに関する以下の質問を参照してください。

#### <a name="youre-new-to-compliance-manager"></a>コンプライアンス マネージャーを使うのは新しい

コンプライアンス マネージャーは、コンプライアンス アクティビティの管理と追跡を行う Microsoft 365 コンプライアンス センターのエンドツーエンドのソリューションです。 初めてアクセスすると、コンプライアンス体制の初期評価が得られるため、コンプライアンスへの取り組み開始には最適な場所です。 以下は、学習を始めるのに良い場所です。

- [コンプライアンス マネージャーの概要を取得する](compliance-manager.md)
- [クイック スタート ガイドを使用して、ステージを上げ進める](compliance-manager-quickstart.md)
- [Microsoft 365 コンプライアンス センターの詳細](microsoft-365-compliance-center.md)

## <a name="are-there-licensing-requirements-for-using-compliance-manager"></a>コンプライアンス マネージャーを使用する場合のライセンス要件はありますか?

はい。 コンプライアンス マネージャーの GA リリースには、新しいライセンス条項が含まれている。 Office 365 ライセンスと Microsoft 365 ライセンスを持つすべての組織、および米国政府機関コミュニティ (GCC) Moderate および GCC High のお客様は、コンプライアンス マネージャーにアクセスできます。 ただし、組織で利用できる評価と評価テンプレートの管理方法は、ライセンス契約によって異なります。 詳細については [、セキュリティとコンプライアンスに関する Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2132371) ライセンス ガイダンスにアクセスしてください。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>ハイ スコアがある場合、完全に準拠しているという意味ですか。

いいえ。 コンプライアンス スコアは、データ保護と規制基準に関するリスクを軽減するのに役立つ推奨アクションを完了する進捗状況を測定します。 これは、特定の標準または規制に関する組織のコンプライアンスの絶対的な測定方法を表すのではありません。 コンプライアンス マネージャーとコンプライアンス スコアは、いかなる方法でも保証と解釈される必要はありません。

## <a name="can-i-use-compliance-manager-for-non-microsoft-products"></a>Microsoft 以外の製品に対してコンプライアンス マネージャーを使用できますか。

コンプライアンス マネージャーは、Microsoft クラウド サービスにのみ継続的な監視と推奨アクションを提供しますが、コンプライアンス マネージャーでサード パーティのサービスのカスタム評価を追加できます。 これにより、Microsoft コンプライアンス マネージャーを SaaS コンプライアンス管理ツールとして使用して、デジタル 資産全体のすべてのコントロールを管理できます。

## <a name="whats-happening-to-compliance-manager-classic-in-the-service-trust-portal"></a>Service Trust Portal のコンプライアンス マネージャー (クラシック) の状況

従来のバージョンのコンプライアンス マネージャーは、Microsoft Service Trust Portal に存在し、間もなく廃止されます。 Microsoft 365 メッセージ センターの通知は、コンプライアンス マネージャー (クラシック) の最終的なサポートがサポートされる少なくとも 60 日前に送信されます。 コンプライアンス マネージャー (クラシック) でコンプライアンス アクティビティを管理しているお客様は、評価やコントロールなどのデータを Microsoft 365 コンプライアンス センターの新しいコンプライアンス マネージャー ソリューションに移行する必要があります。 コンプライアンス マネージャー (クラシック) が廃止された場合、顧客データは Microsoft 365 コンプライアンス センターのコンプライアンス マネージャーに自動的に転送されません。

新しいコンプライアンス マネージャーをすばやくセットアップする方法については、コンプライアンス マネージャーのクイック スタート [ガイドをご覧](compliance-manager-quickstart.md) ください。
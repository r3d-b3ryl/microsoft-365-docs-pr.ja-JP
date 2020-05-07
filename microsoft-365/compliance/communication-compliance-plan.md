---
title: 通信のコンプライアンスを計画する
description: 組織での通信コンプライアンスの使用の計画について説明します。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045852"
---
# <a name="plan-for-communication-compliance"></a>通信のコンプライアンスを計画する

組織での[通信のコンプライアンス](communication-compliance.md)を開始する前に、情報技術およびコンプライアンス管理チームが検討する必要がある重要なアクティビティと考慮事項があります。 以下の領域での展開を完全に理解し、計画することで、コミュニケーション機能の実装と使用がスムーズに進み、ソリューションのベストプラクティスに沿ったものになることができます。

## <a name="work-with-stakeholders-in-your-organization"></a>組織内の関係者と連携する

コミュニケーションコンプライアンス通知に対してアクションを実行するために、組織内の適切なステークホルダーを特定します。 最初の計画とエンドツーエンドの[コミュニケーションのコンプライアンスワークフロー](communication-compliance.md#workflow)については、組織の次の分野に属するユーザーが推奨されます。

- 情報技術
- コンプライアンス
- プライバシー
- セキュリティ
- 人事
- 法務

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>調査と修復のワークフローを計画する

[専任のレビュー担当者] を選択して、 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)の通常のリズムで警告を監視および確認します。 [新しい役割グループを作成](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)して、**監督レビュー管理者**、**ケース管理**、**コンプライアンス管理者**、および**レビュー**の役割を持つレビュー担当者のアクセス許可を有効にして、ポリシーが一致するメッセージを調査および修復する必要があることに注意してください。

## <a name="plan-for-policies"></a>ポリシーを計画する

通信コンプライアンスポリシーの作成は、不快感を持たない言語、機密情報、および規制へのコンプライアンスに関する[事前定義さ](communication-compliance-feature-reference.md#policy-templates)れたテンプレートを使用して、迅速かつ簡単に行うことができます。 カスタム通信コンプライアンスポリシーを使用すると、組織や要件に固有の問題の検出と調査が柔軟になります。

通信コンプライアンスポリシーを計画する場合は、次の点を考慮してください。

- コミュニケーションコンプライアンスポリシーの範囲内として、組織内のすべてのユーザーを追加することを検討してください。 特定のユーザーを個々のポリシーのスコープ内で識別することは、状況によっては便利ですが、多くの組織では、嫌がらせまたは差別検出のために最適化された通信コンプライアンスポリシーのすべてのユーザーを含める必要があります。
- セットアップを簡単にするために、コミュニケーションをレビューする必要があるユーザーのグループを作成することを検討してください。 グループを使用している場合いくつかの必要な場合があります。 たとえば、2つの異なるユーザーグループ間の通信をスキャンする場合、または、監視されていないグループを指定する場合です。
- 確認する通信のパーセンテージを100% に構成して、ポリシーが組織の通信に関する懸念のすべての問題をキャッチするようにします。
- Microsoft 365 組織のメールボックスにインポートされたデータについては、[サードパーティ製のソース](communication-compliance-feature-reference.md#supported-communication-types)からの通信をスキャンすることができます。 これらのプラットフォームでの通信の確認を含めるには、これらのサービスへのコネクタを構成して、メッセージの会議ポリシーの条件が通信ポリシーによって監視されるようにする必要があります。
- ポリシーでは、カスタム通信コンプライアンスポリシーの英語以外の監視言語をサポートできます。 任意の言語で[ユーザー設定のキーワード辞書](communication-compliance-feature-reference.md#custom-keyword-dictionaries)を作成するか、Microsoft 365 の[trainable 分類子](classifier-getting-started-with.md)を使用して独自の machine learning モデルを作成します。
- すべての組織には、異なる通信基準とポリシーニーズがあります。 特定の種類の情報については、通信コンプライアンス[ポリシーの条件](communication-compliance-feature-reference.md#conditional-settings)またはモニターを使用して、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md)を使用して特定のキーワードを監視します。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

Microsoft 365 組織の通信コンプライアンスを構成する方法については、「 [configure communications コンプライアンス For microsoft 365](communication-compliance-configure.md) 」または「 [Contoso 社向けのケーススタディ](communication-compliance-case-study.md)」を参照してください。また、Microsoft Teams、Exchange Online、Yammer の通信で不快な言葉を監視するための通信コンプライアンスポリシーをどのように構成したかを確認してください。

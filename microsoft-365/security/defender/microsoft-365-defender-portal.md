---
title: Microsoft 365 Defender ポータル
description: Microsoft 365 Defender ポータルは、電子メール、コラボレーション、ID、デバイス、アプリの脅威に対する保護、検出、調査、対応を一元的な場所に組み合わせたものです。
keywords: MMicrosoft 365 Defender の概要、サイバー セキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス, ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- admindeeplinkDEFENDER
- intro-overview
ms.topic: conceptual
ms.technology: m365d
adobe-target: true
ms.openlocfilehash: f55172bf0a7df4e15e690a5e0847c81b3cc537dc
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328587"
---
# <a name="microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータル

[Microsoft 365 Defender ポータル](https://sip.security.microsoft.com/homepage?tid=72f988bf-86f1-41af-91ab-2d7cd011db47)は、電子メール、コラボレーション、ID、デバイス、クラウド アプリの脅威に対する保護、検出、調査、および対応を一元的に組み合わせたものです。 Microsoft 365 Defender ポータルは、情報への迅速なアクセス、よりシンプルなレイアウト、およびより簡単に使用できるように関連情報をまとめることを重視しています。 内容は以下のとおりです。

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 は、メールと Office 365 リソースを保護するための一連の防止、検出、調査、およびハンティング機能を使用して、組織が企業を保護するのに役立ちます。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** は、組織内のデバイスに対して、予防的な保護、侵害後の検出、自動調査、および対応を提供します。
- **[Microsoft Defender for Identity](/defender-for-identity/what-is)** は、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダー アクションを特定、検出、調査するためにオンプレミスの Active Directoryシグナルを活用するクラウドベースのセキュリティ ソリューションです。
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)** は、包括的なクロス SaaS および PaaS ソリューションであり、クラウド アプリに対する詳細な可視性、強力なデータ制御、強化された脅威保護を実現します。

Microsoft 365 Defender ポータルの詳細については、この短いビデオをご覧ください。  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBKau]

## <a name="what-to-expect"></a>想定される変化

Microsoft 365 Defender ポータルは、さまざまなワークロードからのシグナルを一連の統合エクスペリエンスに取り込むことで、セキュリティ チームが攻撃を調査して対応する上で役立ちます。

- インシデントとアラート
- 検索
- 申請&アクション
- 脅威の分析
- セキュア スコア
- ラーニング ハブ
- 試験

Microsoft 365 Defenderは *、一致、明確さ、共通の目標を強調します*。 

> [!NOTE]
> Microsoft 365 Defender ポータルにアクセスするのに、お客様が移行手順を実行したり、新しいライセンスを購入したりする必要はありません。 たとえば、この新しいポータルは、Microsoft Defender for Office 365 プラン 1 およびプラン 2 の場合と同様に、E3 サブスクリプションを持つ管理者がアクセスできます。ただし、Exchange Online Protection または Defender for Office 365 プラン 1 のお客様には、サブスクリプション ライセンスでサポートされているセキュリティ機能のみが表示されます。 ポータルの目的は、セキュリティを一元化することです。

## <a name="incident-and-alert-investigations"></a>インシデントとアラートの調査

セキュリティ情報を一元化すると、Microsoft 365 全体でセキュリティ インシデントを調査するための単一の場所が作成されます。 主な例は、**インシデント&アラートの下のインシデントです**。

:::image type="content" source="../../media/converged-incidents-2.png" alt-text="Microsoft 365 Defender ポータルのインシデント ページ" lightbox="../../media/converged-incidents-2.png":::

インシデント名を選択すると、セキュリティ情報を一元化する価値を示すページが表示されます。メールから ID、エンドポイントまで、脅威の完全な拡張に関するより適切な分析情報が得られます。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender のインシデントの概要ページの例" lightbox="../../media/converged-incident-info-3.png":::

時間を取って環境内のインシデントを確認し、各アラートをドリルダウンし、情報にアクセスして分析の次の手順を決定する方法について理解を築く練習を行います。

詳細については、「[Microsoft 365 Defender のインシデント](incidents-overview.md)」を参照してください。

## <a name="hunting"></a>検索
カスタム検出ルールを構築し、環境内の特定の脅威を探すことができます。 **ハンティング** では、クエリベースの脅威検出ツールを使用して、組織内のイベントを事前に検査して脅威のインジケーターとエンティティを見つけることができます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、不適切なマシン、およびその他の結果を確認して対応します。

詳細については、「[Microsoft 365 Defenderでの高度な捜索で脅威をプロアクティブに検出](advanced-hunting-overview.md)する」を参照してください。

## <a name="improved-processes"></a>改善されたプロセス

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードにまとめられて、見つけやすくなります。たとえば、統一された設定などです。

### <a name="unified-settings"></a>統一された設定

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="Microsoft 365 Defender ポータルの設定ページ" lightbox="../../media/converged-add-role-9.png":::

### <a name="permissions--roles"></a>アクセス許可と役割

:::image type="content" source="../../media/converged-roles-5.png" alt-text="アクセス許可 & ロール ページに表示されるエンドポイント ロール & グループ" lightbox="../../media/converged-roles-5.png":::

Microsoft 365 Defender へのアクセスは、Azure AD グローバル ロールまたはカスタム ロールを使用して構成されます。

- [Microsoft 365 Defender へのアクセスを管理する](m365d-permissions.md)方法の詳細
- Microsoft 365 Defender で[カスタム ロールを作成](custom-roles.md)する方法の詳細


### <a name="integrated-reports"></a>統合レポート

レポートは、Microsoft 365 Defender でも統合されます。 管理者は、一般的なセキュリティ レポートから始めて、エンドポイント、メール、コラボレーションに関する特定のレポートに分岐できます。 ここでのリンクは、ワークロード構成に基づいて動的に生成されます。

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

**ホーム** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザーの役割によって異なります。 Microsoft 365 Defender ポータルは役割ベースのアクセス制御を使用しているため、役割が異なれば、日常業務にとってより意味のあるカードが表示されます。

この一目でわかる情報は、組織内の最新の活動についていくのに役立ちます。 Microsoft 365 Defender は、さまざまなソースからの信号をまとめて、Microsoft 365 環境の全体像を示します。

必要に応じて、異なるカードを追加および削除できます。

### <a name="search-across-entities-preview"></a>エンティティ間の検索 (プレビュー)

>[!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。
検索バーはページの上部にあります。 入力すると、エンティティを見つけやすくするための提案が提供されます。 強化された検索結果ページでは、すべてのエンティティからの結果が一元化されます。

Defender for Endpoint と Defender for Identity では、次のエンティティを検索できます。 

- **デバイス** - Defender for Endpoint と Defender for Identity の両方でサポートされます。検索演算子の使用をサポートします。 
- **ユーザー** - Defender for Endpoint、Defender for Identity、Defender for Cloud Apps でサポートされています。 
- **ファイル、IP、URL** - Defender for Endpoint と同じ機能。

    >[!NOTE]
    >IP と URL の検索は完全に一致し、検索結果ページには表示されません – これらは、エンティティ ページに直接誘導されます。 

- **MDVM** - Defender for Endpoint (脆弱性、ソフトウェア、推奨事項) と同じ機能。 

## <a name="threat-analytics"></a>脅威の分析

次のMicrosoft 365 Defender脅威分析を使用して、新たな脅威を追跡して対応します。脅威分析は、Microsoft の専門家のセキュリティ研究者からMicrosoft 365 Defender脅威インテリジェンス ソリューションです。 次のような新たな脅威に直面しながら、セキュリティ チームが可能な限り効率的になるように設計されています。

- アクティブな脅威アクターとそのキャンペーン
- 一般的な攻撃手法と新しい攻撃手法
- 重大な脆弱性
- 一般的な攻撃対象領域
- 流行しているマルウェア

## <a name="learning-hub"></a>Learning Hub

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>には、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、公式ドキュメントなどのリソースからのガイダンスを提供するラーニング ハブが含まれています。

> [!NOTE]
> Microsoft 365 Defender のラーニング ハブの上部には、製品 (現在、Microsoft 365 Defender、Microsoft Defender for Endpoint、および Microsoft Defender for Office 365) から選択できる便利な **フィルター** があります。 各セクションの学習リソースの数がリストされていることに注意してください。これは、学習者がトレーニングと学習のために手元にあるリソースの数を追跡するのに役立ちます。
>
> 製品フィルターに沿って、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する知識または経験のレベル、セキュリティの役割、および製品の機能が一覧表示されます。

> [!TIP]
> [Microsoft Learn](/learn/) には、他にも多くの学習機会があります。 [コース MS-500T02-A: Microsoft 365 脅威に対する保護の実装](/learn/certifications/courses/ms-500t02)などといった認定トレーニングがあります。

## <a name="send-us-your-feedback"></a>フィードバックの送信

あなたのフィードバックが必要です。私たちは常に改善を求めているため、視聴を希望する対象がある場合は、[このビデオを視聴して、私達が皆様のフィードバックを読むことが、皆様から私達への信頼を築く方法であることをご確認ください](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

## <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>Microsoft 365 Defender ポータルで提供される内容を確認する

Microsoft 365 Defender の機能を引き続き確認します。

- [インシデントとアラートを管理する](manage-incidents.md)
- [脅威の分析を使用して、新たな脅威を追跡し対応する](threat-analytics.md)
- [アクション センター](m365d-action-center.md)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](./custom-detection-rules.md)
- [メールとコラボレーションのアラート](../../compliance/alert-policies.md#default-alert-policies)
- [フィッシング攻撃のシミュレーションを作成し](../office-365-security/attack-simulation-training.md)、[チームをトレーニングするためのペイロードを作成する](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn からのこのラーニング パスを使用すると、Microsoft 365 Defender と、それがセキュリティ上の脅威を特定、制御、修復するのにどのように役立つかを理解できます。

|トレーニング: |Microsoft 365 Defender を使用してサイバー攻撃を検出して対応する|
|---|---|
|![Microsoft 365 Defender トレーニング アイコン。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender では、エンドポイント、ID、メール、アプリケーション間で脅威信号を統合し、巧妙なサイバー攻撃を包括的に保護することができます。 Microsoft 365 Defender は、インシデントを調査して対応し、継続的な悪意のあるサイバー セキュリティ活動を積極的に検索することができる中心的な環境です。<p> 1 時間 38 分 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender の新機能](whats-new.md)
- [Microsoft 365 Defender の Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)

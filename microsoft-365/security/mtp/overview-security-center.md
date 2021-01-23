---
title: 概要 - Microsoft 365 セキュリティ センター
description: Microsoft 365 のセキュリティを使用して、Microsoft の ID、データ、デバイス、アプリ全体のセキュリティを監視および管理する方法について説明します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, ID, データ, デバイス, アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: b47ec915bc9f5f51df8ed425e7bfd76966bb989e
ms.sourcegitcommit: 8b3ff6e9f8931327b6f0541fd882107687cd123e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2021
ms.locfileid: "49942780"
---
# <a name="overview-of-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>
進化し続ける脅威から保護するためにビジネスのセキュリティを管理すると、多くの課題が生じることができます。 さまざまな場所で多数のコントロールを構成するセキュリティ ソリューションが多すぎる可能性があります。 どのコントロールが最も効果的で、従業員にとって新しい課題を生み出すのかを知るのに苦労する場合があります。 セキュリティ チームがセキュリティと生産性の適切なバランスを見つけるのは困難な場合があります。

Microsoft 365 セキュリティ センターに入ります。Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するための新しいホームです。 ここでは、組織のセキュリティの正常性を簡単に表示し、デバイス、ユーザー、アプリを構成し、疑わしいアクティビティに関するアラートを取得できます。 Microsoft 365 セキュリティ センターは、セキュリティ管理者とセキュリティ運用チームが組織を管理および保護することを目的とします。

新しい Microsoft 365 セキュリティ センターと [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) コンプライアンス センターは、セキュリティおよびコンプライアンス チームのニーズを満たして設計された特殊なワークスペースです。 これらのソリューションは、Microsoft 365 サービス全体に統合され、リスクを軽減し、デジタル資産を保護するのに役立つ操作可能な分析情報を提供します。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BmvV]

Microsoft 365 セキュリティ センターにアクセスしてください [https://security.microsoft.com](https://security.microsoft.com) 。 

> [!NOTE]
> Microsoft 365 セキュリティ センターにアクセスするには、グローバル管理者、セキュリティ管理者、セキュリティオペレーター、Azure Active Directory のセキュリティ 閲覧者などの適切なロールが割り当てられている必要があります。

## <a name="at-a-glance-view-of-your-microsoft-365-environment"></a>Microsoft 365 環境の概要

ホーム **ページには** 、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザー ロールによって異なります。 Microsoft 365 セキュリティ センターでは役割ベースのアクセス制御が使用されるので、さまざまな役割で、毎日のジョブにとってより有意義なカードが表示されます。  

この一目でわかる情報は、組織内の最新のアクティビティを把握するのに役立ちます。 Microsoft 365 セキュリティ センターは、さまざまなソースからのシグナルをまとめ、Microsoft 365 環境の全体像を表示します。

大別すると、カードは次のカテゴリに分類されます。

- **ID -** 組織内の ID を監視し、疑わしい動作や危険な動作を追跡します。 [ID 保護の詳細](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **データ** - 許可されていないデータの漏えいにつながる可能性があるユーザーアクティビティを追跡するのに役立ちます。
- **デバイス** - デバイス上のアラート、違反アクティビティ、その他の脅威に関する最新の情報を取得します。
- **アプリ** - クラウド アプリが組織でどのように使用されているのかについての洞察を得る。 [Cloud App Security で検出されたアプリについて詳しくは、次のリンクを参照してください。](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="explore-what-the-security-center-has-to-offer"></a>セキュリティ センターで提供する必要がある機能を確認する

Microsoft 365 セキュリティ センターには以下のものが含まれます。

* **ホーム** – 組織の全体的なセキュリティの正常性を一目で確認できます。
* **インシデント** - エンティティの個々のアラートに表示されるドットを接続して、攻撃のより広範なストーリーを確認します。 攻撃が開始された場所、影響を受けるデバイス、影響を受けたユーザー、脅威が出た場所を正確に確認できます。
* **アラート** – Microsoft 365 環境全体のすべてのアラートを詳細に表示できます。 Microsoft Cloud App Security、Office 365 用 Microsoft Defender、Azure Active Directory、Id 用 Microsoft Defender、およびエンドポイント用 Microsoft Defender からのアラートが含まれます。 E3 および E5 のお客様が利用できます。  
* **アクション センター** - セキュリティ チームが手動で対処する必要がある警告の量を減らし、セキュリティ運用チームは、より高度な脅威や他の価値の高いイニシアチブに集中できます。
* **レポート** – ユーザー、デバイス、アプリなどをより良く保護するために必要な詳細情報と情報を取得します。
* **セキュア スコア** - Microsoft セキュア スコアを使用して、全体的なセキュリティ体制を改善します。 このページでは、有効にしたさまざまなセキュリティ機能の概要と、改善する領域に関する推奨事項を示します。
* **高度な捜** 索 – Microsoft 365 組織内のマルウェア、疑わしいファイル、アクティビティを積極的に検索します。
* **分類** - ラベルを追加してドキュメント、メール メッセージ、ドキュメント、サイトなどを分類することにより、データ損失を防ぎます。 ラベルが (自動的またはユーザーによって) 適用されると、選択した設定に基づいてコンテンツまたはサイトが保護されます。 たとえば、ファイルを暗号化し、コンテンツ マーキングを追加し、特定のサイトへのユーザー アクセスを制御するラベルを作成できます。
* **ポリシー** - デバイスを管理し、脅威から保護し、組織内のさまざまなアクティビティに関するアラートを受信するためのポリシーを設定します。
* **アクセス許可** - Microsoft 365 セキュリティ センターでコンテンツの表示とタスクの実行にアクセスできる組織内のユーザーを管理します。 Azure AD ポータルで Microsoft 365 のアクセス許可を割り当てることもできます。

## <a name="learn-more"></a>詳細情報

セキュリティ ニーズの監視、確認、対応に関する以下のトピックを参照してください。

- インシデントを通じてアラートのドット [を接続する](incident-queue.md)
- 自動調査と修復を使用 [して脅威を自動的に修復する](mtp-autoir.md)
- Microsoft セキュア スコアを使用して、セキュリティの体勢を全体的 [に確認および改善する](microsoft-secure-score.md)
- ネットワーク [上のデバイス](device-profile.md) を表示する
- [ID、](monitoring-and-reporting.md) データ、デバイス、アプリ、インフラストラクチャの状態を報告する
- [メール、データ、デバイス、アカウント](advanced-hunting-overview.md) に影響を与える侵入の試みと侵害アクティビティに対する脅威を事前に検出する
- [脅威分析による最新の攻撃](latest-attack-campaigns.md) キャンペーンと手法を理解する

## <a name="see-also"></a>関連項目

- [Microsoft セキュリティ ポータル](portals.md)

---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップして、組織内のデバイス、ID、データ、アプリケーションを保護するように設計されたセキュリティ ソリューションを試して体験します。
keywords: Microsoft 365 Defender 試用版、Microsoft 365 Defender の試用、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933171"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、ユーザーとグループを使用してラボ環境をセットアップする場合に役立ち、脅威攻撃を模倣して有意義な試用結果を得るために、Microsoft 365 Defender の機能の構成をガイドします。 

この試用版ラボまたはパイロット環境を作成する目的は、Microsoft 365 Defender の包括的で統合された機能を説明する目的です。 このインテリジェント セキュリティ ソリューションが組織の高度な脅威を検出、防止、自動的に調査、および対応する方法を体験してください。 


推奨される展開パスに基づいて Microsoft 365 Defender 評価を開始する手順について説明します。 目標は、試用版アカウントを使用してラボ環境で、またはフル ライセンスを使用して実稼働環境でセキュリティ ソリューションをセットアップする場合に役立ちます。 試用版ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作の使用例を提示するのに役立ちます。 攻撃シミュレーションの実行が完了し、結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の助けを借りて、組織に完全に展開して運用できます。 

このガイドは、次の場合に役立ちます。
- ラボ サーバーとコンピューターのセットアップ
- ユーザーとグループを使用して Active Directory を構成する
- Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、Microsoft Cloud App Security のセットアップと構成
- サーバーとコンピューターのローカル ポリシーを設定する
- Microsoft 365 Defender でテスト インシデントまたはアラートを生成する脅威攻撃を模倣する

>[!IMPORTANT]
>最適な結果を得る場合は、可能な限りラボのセットアップ手順に従います。


## <a name="deployment-phases"></a>展開フェーズ

Microsoft 365 Defender 試用版ラボ環境の作成には 3 つのフェーズがあります。

![展開フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|段階 | 説明 | 
|:-------|:-----|
|[フェーズ 1: 準備](prepare-m365d-eval.md)| 試用版ラボまたはパイロット環境で Microsoft 365 Defender を展開する際に考慮する必要がある点について説明します。 <br><br>- 関係者とサインオフ <br> - 環境に関する考慮事項 <br>- Access <br>- Azure Active Directory のセットアップ <br> - 構成順序
|[フェーズ 2: セットアップ](setup-m365deval.md)|  Microsoft 365 セキュリティ センターにアクセスする最初の手順を実行して、Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップします。 次の情報に案内されます。<br><br>- Microsoft 365 E5 試用版にサインアップする <br>  - ドメインの構成<br>- Microsoft 365 E5 ライセンスの割り当て<br>- ポータルでセットアップ ウィザードを完了する|
|[フェーズ 3: オンボードで&する](config-m365d-eval.md) | 各 Microsoft 365 Defender の柱とオンボード エンドポイントを構成します。 次の情報に案内されます。<br><br>- Microsoft Defender for Office 365<br>- Microsoft Cloud App Security の構成<br>- Id 用に Microsoft Defender を構成する<br>- エンドポイント用の Microsoft Defender の構成


このガイドを完了すると、関係する関係者と必要な承認を特定し、適切なアクセス許可を持ち、試用版にサインアップし、ドメインを構成し、Microsoft 365 Defender の各柱を構成し、エンドポイントがサービスにオンボードされます。

## <a name="key-capabilities"></a>主な機能

Microsoft 365 Defender には多くの機能があります。この展開ガイドの主な目的は、デバイスのオンボードを開始する方法です。 オンボーディングに加えて、このガイダンスでは、次の機能を使用して開始できます。


機能 | 説明 
:---|:---
Microsoft Defender for Office 365 | 今日の脅威から 365 のOffice全体を保護するのに役立ちます
Microsoft Defender for Identity | 侵害された ID および悪意のあるインサイダーアクションに対する脅威を識別および検出します。
Microsoft Cloud App Security | 豊富な可視性、データ移動の制御、クラウド サービス全体のサイバー脅威の検出を提供します。
Microsoft Defender for Endpoint | 包括的なエンドポイント セキュリティを使用して、高度な脅威に対する対応機能を防止、検出、および提供します。


## <a name="in-scope"></a>スコープ内

このガイドでは、以下のタスクが対象になります。
-   Azure Active Directory をセットアップする
-   Microsoft 365 Defender のセットアップ
    -   パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、フル ライセンスを使用する
    -   ドメインの構成
    -   Microsoft 365 E5 ライセンスの割り当て
    -   ポータル内でのセットアップ ウィザードの完了
-   ベスト プラクティスに基づいてすべての Microsoft 365 Defender の柱を構成する
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>対象外

以下は、この展開ガイドの範囲を外しています。

-   Microsoft 365 Defender と統合する可能性のあるサード パーティ製ソリューションの構成
-   実稼働環境での侵入テスト

## <a name="next-step"></a>次の手順
[フェーズ 1: 準備](prepare-m365d-eval.md) 
<br> Microsoft 365 Defender 試用版ラボまたはパイロット環境を準備する

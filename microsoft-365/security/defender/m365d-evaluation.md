---
title: Microsoft 365 Defender を評価する
description: 組織のMicrosoft 365 Defender、ID、データ、およびアプリケーションを保護するように設計されたセキュリティ ソリューションを試して体験するように、Microsoft 365 Defender試用版ラボまたはパイロット環境をセットアップします。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
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
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458425"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>試用版ラボMicrosoft 365 Defenderパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、ユーザーとグループを使用してラボ環境をセットアップする全体にわたって作業し、Microsoft 365 Defender の機能の構成をガイドして、脅威攻撃を模倣し、有意義な試用結果を得るのに役立ちます。 

この試用版ラボまたはパイロット環境を作成する目的は、包括的で統合されたテスト機能をMicrosoft 365 Defenderです。 このインテリジェント セキュリティ ソリューションが組織の高度な脅威を検出、防止、自動的に調査、および対応する方法を体験してください。 


推奨される展開パスに基づいて、Microsoft 365 Defender評価を開始する手順について説明します。 目標は、試用版アカウントを使用してラボ環境で、またはフル ライセンスを使用して実稼働環境でセキュリティ ソリューションをセットアップする場合に役立ちます。 試用版ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作の使用例を提示するのに役立ちます。 攻撃シミュレーションの実行が完了し、結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の助けを借りて、組織に完全に展開して運用できます。 

このガイドは、次の場合に役立ちます。
- ラボ サーバーとコンピューターのセットアップ
- ユーザーとグループを使用して Active Directory を構成する
- Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、および Microsoft Cloud App Security
- サーバーとコンピューターのローカル ポリシーを設定する
- 脅威攻撃を模倣して、テスト インシデントまたはアラートを生成Microsoft 365 Defender

>[!IMPORTANT]
>最適な結果を得る場合は、可能な限りラボのセットアップ手順に従います。


## <a name="deployment-phases"></a>展開フェーズ

試用版ラボ環境の作成には 3 つのMicrosoft 365 Defenderがあります。

![展開フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|段階 | 説明 | 
|:-------|:-----|
|[フェーズ 1: 準備](prepare-m365d-eval.md)| 試用版ラボまたはパイロット環境にMicrosoft 365 Defender検討する必要がある点について説明します。 <br><br>- 関係者とサインオフ <br> - 環境に関する考慮事項 <br>- Access <br>- Azure Active Directoryセットアップ <br> - 構成順序
|[フェーズ 2: セットアップ](setup-m365deval.md)|  最初の手順を実行して、Microsoft 365セキュリティ センターにアクセスして、試用版ラボまたはMicrosoft 365 Defender環境をセットアップします。 次の情報に案内されます。<br><br>- 試用版にMicrosoft 365 E5する <br>  - ドメインの構成<br>- ライセンスMicrosoft 365 E5割り当てる<br>- ポータルでセットアップ ウィザードを完了する|
|[フェーズ 3: オンボードで&する](config-m365d-eval.md) | ピラーエンドポイントMicrosoft 365 Defenderオンボード エンドポイントを構成します。 次の情報に案内されます。<br><br>- Microsoft Defender for Office 365<br>- 構成Microsoft Cloud App Security<br>- Id 用に Microsoft Defender を構成する<br>- エンドポイント用の Microsoft Defender の構成


このガイドを完了すると、関係する関係者と必要な承認を特定し、適切なアクセス許可を持ち、試用版、構成済みのドメイン、および各 Microsoft 365 Defender の柱にサインアップし、エンドポイントがサービスにオンボードされます。

## <a name="key-capabilities"></a>主な機能

このMicrosoft 365 Defender機能を提供しますが、この展開ガイドの主な目的は、デバイスのオンボーディングを開始する方法です。 オンボーディングに加えて、このガイダンスでは、次の機能を使用して開始できます。


機能 | 説明 
:---|:---
Microsoft Defender for Office 365 | 今日の脅威からOffice 365全体を保護するのに役立ちます
Microsoft Defender for Identity | 侵害された ID および悪意のあるインサイダーアクションに対する脅威を識別および検出します。
Microsoft Cloud App Security | 豊富な可視性、データ移動の制御、クラウド サービス全体のサイバー脅威の検出を提供します。
Microsoft Defender for Endpoint | 包括的なエンドポイント セキュリティを使用して、高度な脅威に対する対応機能を防止、検出、および提供します。


## <a name="in-scope"></a>スコープ内

このガイドでは、以下のタスクが対象になります。
-   Azure Active Directory をセットアップする
-   設定Microsoft 365 Defender
    -   パイロットを実行しているMicrosoft 365 E5試用版にサインアップするか、フル ライセンスを使用する
    -   ドメインの構成
    -   ライセンスMicrosoft 365 E5割り当てる
    -   ポータル内でのセットアップ ウィザードの完了
-   ベスト プラクティスにMicrosoft 365 Defender、すべての柱を構成する
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>対象外

以下は、この展開ガイドの範囲を外しています。

-   アプリケーションと統合する可能性のあるサード パーティ製ソリューションのMicrosoft 365 Defender
-   実稼働環境での侵入テスト

## <a name="next-step"></a>次の手順
[フェーズ 1: 準備](prepare-m365d-eval.md) 
<br> テスト ラボMicrosoft 365 Defenderパイロット環境を準備する

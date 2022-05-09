---
title: Microsoft 365 Defender を評価する
description: 組織内のデバイス、ID、データ、アプリケーションを保護するように設計されたセキュリティ ソリューションを試して体験するように、Microsoft 365 Defender試用版ラボまたはパイロット環境を設定します。
keywords: 試用版のMicrosoft 365 Defender、Microsoft 365 Defenderの試用、Microsoft 365 Defenderの評価、評価ラボのMicrosoft 365 Defender、Microsoft 365 Defender パイロット、サイバー セキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜索
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
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender試用版ラボまたはパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、ユーザーとグループを使用してラボ環境をセットアップする際に役立ちます。その後、脅威攻撃を模倣し、意味のある試用版の結果を得ることができるように、Microsoft 365 Defenderの機能の構成について説明します。 

この試用版ラボまたはパイロット環境を作成する目的は、包括的で統合されたMicrosoft 365 Defender機能を説明することです。 このインテリジェント セキュリティ ソリューションが、組織の高度な脅威を検出、防止、自動的に調査、および対応する方法について説明します。 


推奨されるデプロイ パスに基づいてMicrosoft 365 Defender評価を開始する手順について説明します。 目標は、試用版アカウントを持つラボ環境で、または完全なライセンスを持つ運用環境のパイロット環境で、セキュリティ ソリューションを設定するのに役立ちます。 試用版ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作のユース ケースを提示するのに役立ちます。 攻撃シミュレーションの実行が完了し、結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の助けを借りて、組織内で完全に展開して運用化できます。 

このガイドは、次の役に立ちます。
- ラボ サーバーとコンピューターを設定する
- ユーザーとグループを使用して Active Directory を構成する
- Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、およびMicrosoft Cloud App Security
- サーバーとコンピューターのローカル ポリシーを設定する
- 脅威攻撃を模倣して、Microsoft 365 Defenderでテスト インシデントまたはアラートを生成する

>[!IMPORTANT]
>最適な結果を得るには、ラボのセットアップ手順にできるだけ近い手順に従ってください。


## <a name="deployment-phases"></a>展開フェーズ

Microsoft 365 Defender試用版ラボ環境の作成には、3 つのフェーズがあります。

![デプロイ フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|段階 | 説明 | 
|:-------|:-----|
|[フェーズ 1: 準備](prepare-m365d-eval.md)| 試用版ラボまたはパイロット環境にMicrosoft 365 Defenderを展開する際に考慮する必要がある事項について説明します。 <br><br>- 関係者とサインオフ <br> - 環境に関する考慮事項 <br>- アクセス <br>- Azure Active Directoryセットアップ <br> - 構成順序
|[フェーズ 2: セットアップ](setup-m365deval.md)|  Microsoft 365 Security Center にアクセスして、Microsoft 365 Defender試用版ラボまたはパイロット環境を設定するための最初の手順を実行します。 次の手順に従います。<br><br>- Microsoft 365 E5試用版にサインアップする <br>  - ドメインを構成する<br>- Microsoft 365 E5 ライセンスを割り当てる<br>- ポータルでセットアップ ウィザードを完了する|
|[フェーズ 3: オンボード&構成する](config-m365d-eval.md) | 各Microsoft 365 Defenderの柱とオンボード エンドポイントを構成します。 次の手順に従います。<br><br>- Microsoft Defender for Office 365を構成する<br>- Microsoft Cloud App Securityを構成する<br>- Microsoft Defender for Identityを構成する<br>- Microsoft Defender for Endpointを構成する


このガイドを完了すると、関係者と必要な承認が特定され、適切なアクセス許可が付与され、試用版にサインアップされ、ドメインが構成され、各Microsoft 365 Defenderの柱が作成され、エンドポイントがサービスにオンボードされます。

## <a name="key-capabilities"></a>主な機能

Microsoft 365 Defenderには多くの機能が用意されていますが、この展開ガイドの主な目的は、デバイスのオンボードを開始することです。 このガイダンスでは、オンボードに加えて、次の機能の使用を開始します。


機能 | 説明 
:---|:---
Microsoft Defender for Office 365 | 今日の脅威からOffice 365環境全体を保護するのに役立ちます
Microsoft Defender for Identity | 侵害された ID と悪意のあるインサイダー アクションに対する脅威を識別して検出します。
Microsoft Cloud App Security | 豊富な可視性を提供し、データの移動を制御し、クラウド サービス全体のサイバー脅威を検出します。
Microsoft Defender for Endpoint | 包括的なエンドポイント セキュリティにより、高度な脅威に対する対応機能を防止、検出、および提供します。


## <a name="in-scope"></a>スコープ内

このガイドのスコープには、次のタスクがあります。
-   Azure Active Directory をセットアップする
-   Microsoft 365 Defenderを設定する
    -   Microsoft 365 E5試用版にサインアップするか、パイロットを実行している場合はフル ライセンスを使用します
    -   ドメインを構成する
    -   Microsoft 365 E5 ライセンスを割り当てる
    -   ポータル内でセットアップ ウィザードを完了する
-   ベスト プラクティスに基づいてすべてのMicrosoft 365 Defenderの柱を構成する
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>対象外

このデプロイ ガイドの範囲外は次のとおりです。

-   Microsoft 365 Defenderと統合される可能性があるサード パーティソリューションの構成
-   運用環境での侵入テスト

## <a name="next-step"></a>次の手順
[フェーズ 1: 準備](prepare-m365d-eval.md) 
<br> Microsoft 365 Defender試用版ラボまたはパイロット環境を準備する

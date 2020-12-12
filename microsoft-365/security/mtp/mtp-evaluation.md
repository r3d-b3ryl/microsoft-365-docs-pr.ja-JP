---
title: Microsoft 365 Defender を評価する
description: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップし、組織内のデバイス、ID、データ、アプリケーションを保護するために設計されたセキュリティ ソリューションを試して体験します。
keywords: Microsoft Threat Protection 試用版、Microsoft Threat Protection の評価、Microsoft Threat Protection 評価ラボ、Microsoft Threat Protection パイロット、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜問
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659635"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、ユーザーとグループを含むラボ環境の設定に関する作業を行うのに役立ち、Microsoft 365 Defender の機能の構成について説明します。これにより、脅威攻撃を模倣し、意味のある評価版の結果を得ることができます。 

この試験ラボまたはパイロット環境を作成する目的は、Microsoft 365 Defender の包括的で統合された機能を説明する目的です。 このインテリジェント なセキュリティ ソリューションが、組織の高度な脅威を検出、防止、自動的に調査、および対応する方法を体験します。 


推奨される展開パスに基づいて Microsoft 365 Defender の評価を開始する手順について説明します。 目標は、試験アカウントを使用したラボ環境、またはフル ライセンスの実稼働環境でのセキュリティ ソリューションのセットアップを支援します。 試験ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作の使用事例を提示するのに役立ちます。 攻撃シミュレーションの実行が完了し、結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の支援を受け、組織に完全に展開して運用することができます。 

このガイドは、次の場合に役立ちます。
- ラボ サーバーとコンピューターをセットアップする
- ユーザーとグループを使用して Active Directory を構成する
- Id 用に Microsoft Defender、Office 365 用 Microsoft Defender、エンドポイント用 Microsoft Defender、Microsoft Cloud App Security をセットアップして構成する
- サーバーとコンピューターのローカル ポリシーを設定する
- 脅威攻撃を模倣して Microsoft 365 Defender でテスト インシデントまたはアラートを生成する

>[!IMPORTANT]
>最適な結果を得る場合は、できる限りラボのセットアップ手順に従ってください。


## <a name="deployment-phases"></a>展開フェーズ

Microsoft 365 Defender 試用版ラボ環境を作成するには、3 つのフェーズがあります。

![展開フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|フェーズ | 内容 | 
|:-------|:-----|
|[フェーズ 1: 準備](prepare-mtpeval.md)| 試用版ラボまたはパイロット環境で Microsoft 365 Defender を展開する際に考慮する必要がある点について説明します。 <br><br>- 関係者とサインオフ <br> - 環境に関する考慮事項 <br>- Access <br>- Azure Active Directory のセットアップ <br> - 構成順序
|[フェーズ 2: セットアップ](setup-mtpeval.md)|  最初の手順を実行して、Microsoft 365 セキュリティ センターにアクセスし、Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップします。 次のガイドが表示されます。<br><br>- Microsoft 365 E5 試用版にサインアップする <br>  - ドメインを構成する<br>- Microsoft 365 E5 ライセンスを割り当てる<br>- ポータルでセットアップ ウィザードを完了する|
|[フェーズ 3: オンボードの&構成](config-mtpeval.md) | 各 Microsoft 365 Defender の柱とオンボード エンドポイントを構成します。 次のガイドが表示されます。<br><br>- Microsoft Defender を Office 365 用に構成する<br>- Microsoft Cloud App Security を構成する<br>- Id 用に Microsoft Defender を構成する<br>- エンドポイント用に Microsoft Defender を構成する


このガイドを完了すると、関係する関係者と必要な承認を特定し、適切なアクセス許可を持ち、試用版にサインアップし、ドメインを構成し、Microsoft 365 Defender の各柱を構成すると、エンドポイントがサービスにオンボードされます。

## <a name="key-capabilities"></a>主な機能

Microsoft 365 Defender は多くの機能を提供しますが、この展開ガイドの主な目的は、デバイスのオンボーディングを開始することで開始します。 オンボーディングに加えて、このガイダンスでは次の機能を開始できます。


機能 | 説明 
:---|:---
Microsoft Defender for Office 365 | 今日の脅威から 365 Office全体を保護するのに役立ちます
Microsoft Defender for Identity | 侵害された ID と悪意のあるインサイダーアクションに対する脅威を特定し、検出します。
Microsoft Cloud App Security | 豊富な可視性を提供し、データの移動を制御し、クラウド サービス全体のサイバー脅威を検出します。
Microsoft Defender for Endpoint | 包括的なエンドポイント セキュリティを使用して、高度な脅威に対する対応機能を防止、検出、および提供します。


## <a name="in-scope"></a>スコープ内

このガイドの対象タスクは次のとおりです。
-   Azure Active Directory のセットアップ
-   Microsoft 365 Defender のセットアップ
    -   Microsoft 365 E5 試用版にサインアップするか、パイロットを実行している場合は完全なライセンスを使用する
    -   ドメインを構成する
    -   Microsoft 365 E5 ライセンスを割り当てる
    -   ポータル内でセットアップ ウィザードを完了する
-   ベスト プラクティスに基づいてすべての Microsoft 365 Defender の柱を構成する
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>対象外

この展開ガイドの対象範囲を次に示します。

-   Microsoft 365 Defender と統合される可能性があるサード パーティ製ソリューションの構成
-   実稼働環境での侵入テスト

## <a name="next-step"></a>次の手順
[フェーズ 1: 準備](prepare-mtpeval.md) 
<br> Microsoft 365 Defender 試用版ラボまたはパイロット環境を準備する

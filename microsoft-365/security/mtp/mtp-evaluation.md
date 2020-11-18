---
title: Microsoft 365 Defender を評価する
description: Microsoft 365 Defender 試用ラボまたはパイロット環境を設定して、組織内のデバイス、id、データ、およびアプリケーションを保護するために設計されたセキュリティソリューションを体験してみてください。
keywords: Microsoft threat Protection の試用版、microsoft threat protection の評価、microsoft の脅威保護の評価ラボ、microsoft の脅威保護のパイロット、サイバーセキュリティ、高度な脅威、企業のセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130890"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender 試用ラボまたはパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

この試用ラボまたはパイロット環境を作成する目的は、包括的かつ統合された Microsoft 365 Defender 機能を説明することです。 このインテリジェントセキュリティソリューションが組織に対する高度な脅威を検出、阻止、自動調査、および応答する方法について説明します。 

このガイドでは、推奨される展開パスに基づいて Microsoft 365 Defender 評価を開始する手順について説明します。 ここでの目的は、試用版アカウントを使用したラボ環境で、または完全ライセンスを使用した運用環境で、セキュリティソリューションをセットアップできるようにすることです。 試用ラボまたはパイロット環境の準備は、組織の意思決定者にセキュリティ操作の使用ケースを提示するのに役立ちます。 攻撃のシミュレーションの実行が完了し、結果に問題がなければ、組織内の Microsoft テクニカルセールス担当者または専門家と協力して、組織内で operationalize it を完全に展開し、その結果を得ることができます。 

このガイドは、次のことを支援します。
- ラボサーバーとコンピューターをセットアップする
- ユーザーおよびグループを使用して Active Directory を構成する
- Id に対して Microsoft Defender をセットアップおよび構成する、Microsoft Defender for Office 365、Microsoft defender for Endpoint、microsoft Cloud App Security
- サーバーとコンピューターのローカルポリシーをセットアップする
- Microsoft 365 Defender でテストインシデントまたはアラートを生成する脅威攻撃を模倣する

>[!IMPORTANT]
>最適な結果を得るには、演習のセットアップの指示に従ってください。


## <a name="deployment-phases"></a>展開フェーズ

Microsoft 365 Defender 試用ラボ環境を作成して展開するには、3つのフェーズがあります。

![展開フェーズ: 準備、セットアップ、オンボード](../../media/phase-diagrams/deployment-phases.png)

|フェーズ | 説明 | 
|:-------|:-----|
|[フェーズ 1: 準備](prepare-mtpeval.md)| トライアルラボまたはパイロット環境に Microsoft 365 Defender を展開するときに考慮する必要がある事項について説明します。 <br><br>-関係者と承認 <br> -環境に関する考慮事項 <br>-アクセス <br>-Azure Active Directory のセットアップ <br> -構成の順序
|[フェーズ 2: セットアップ](setup-mtpeval.md)|  Microsoft 365 セキュリティセンターにアクセスするための最初の手順を実行して、Microsoft 365 Defender 試用ラボまたはパイロット環境を設定します。 次のようなガイドが表示されます。<br><br>-Microsoft 365 E5 試用版にサインアップする <br>  -ドメインの構成<br>-Microsoft 365 E5 ライセンスを割り当てる<br>-ポータルのセットアップウィザードを完了します。|
|[フェーズ 3: 構成 & オンボード](config-mtpeval.md) | 各 Microsoft 365 Defender 柱およびオンボードエンドポイントを構成します。 次のようなガイドが表示されます。<br><br>-Office 365 の Microsoft Defender を構成する<br>-Microsoft Cloud App Security を構成する<br>-Identity の Microsoft Defender を構成する<br>-エンドポイントの Microsoft Defender を構成する


## <a name="in-scope"></a>範囲内

このガイドの対象となるタスクは次のとおりです。
-   Azure Active Directory をセットアップする
-   Microsoft 365 Defender をセットアップする
    -   パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、完全ライセンスを使用します。
    -   ドメインを構成する
    -   Microsoft 365 E5 ライセンスを割り当てる
    -   ポータル内のセットアップウィザードの完了
-   ベストプラクティスに基づいてすべての Microsoft 365 Defender 柱を構成する
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>対象外

この展開ガイドの範囲外のものを以下に示します。

-   Microsoft 365 Defender と統合される可能性のあるサードパーティ製ソリューションの構成
-   運用環境でのペネトレーションテスト

## <a name="next-step"></a>次の手順
[フェーズ 1: 準備](prepare-mtpeval.md) 
<br> Microsoft 365 Defender 試用ラボまたはパイロット環境の準備

---
title: Microsoft Threat Protection を評価する
description: 組織内のデバイス、id、データ、およびアプリケーションを保護するために設計されたセキュリティソリューションを体験して、Microsoft の脅威保護の試用ラボまたはパイロット環境を設定します。
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447121"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Microsoft の脅威保護の試用ラボまたはパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

この試用版またはパイロット環境を作成する目的は、包括的かつ統合された Microsoft の脅威保護機能を理解することです。 このインテリジェントセキュリティソリューションが組織に対する高度な脅威を検出、阻止、自動調査、および応答する方法について説明します。 

このガイドでは、推奨される展開パスに基づいて Microsoft の脅威保護評価を開始する手順について説明します。 ここでの目的は、試用版アカウントを使用したラボ環境で、または完全ライセンスを使用した運用環境で、セキュリティソリューションをセットアップできるようにすることです。 試用ラボまたはパイロット環境の準備は、組織の意思決定者にセキュリティ操作の使用ケースを提示するのに役立ちます。 攻撃のシミュレーションの実行が完了し、結果に問題がなければ、組織内の Microsoft テクニカルセールス担当者または専門家と協力して、組織内で operationalize it を完全に展開し、その結果を得ることができます。 

このガイドは、次のことを支援します。
- ラボサーバーとコンピューターをセットアップする
- ユーザーおよびグループを使用して Active Directory を構成する
- Azure ATP、Office ATP、Microsoft Defender ATP、および Microsoft Cloud App Security を設定および構成する
- サーバーとコンピューターのローカルポリシーをセットアップする
- Microsoft の脅威保護でテストインシデントまたはアラートを生成する脅威攻撃を模倣する

>[!IMPORTANT]
>最適な結果を得るには、演習のセットアップの指示に従ってください。


## <a name="deployment-phases"></a>展開フェーズ

Microsoft の脅威保護のテスト環境を作成して展開するには、3つのフェーズがあります。

|フェーズ | 説明 | 
|:-------|:-----|
| ![フェーズ 1: 準備](../../media/prepare.png)<br>[フェーズ 1: 準備](prepare-mtpeval.md)| マイクロソフトの脅威保護を試用ラボまたはパイロット環境に展開するときに考慮する必要があることについて説明します。 <br><br>-関係者と承認 <br> -環境に関する考慮事項 <br>-アクセス <br>-Azure Active Directory のセットアップ <br> -構成の順序
|  ![フェーズ 2: セットアップ](../../media/setup.png) <br>[フェーズ 2: セットアップ](setup-mtpeval.md)|  最初の手順を実行して、microsoft 365 セキュリティセンターにアクセスし、Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップします。 次のようなガイドが表示されます。<br><br>-Microsoft 365 E5 試用版にサインアップする <br>  -ドメインの構成<br>-Microsoft 365 E5 ライセンスを割り当てる<br>-ポータルのセットアップウィザードを完了します。|
|  ![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png) <br>[フェーズ 3: 構成 & オンボード](config-mtpeval.md) | Microsoft の各脅威保護の柱とオンボードエンドポイントを構成します。 次のようなガイドが表示されます。<br><br>-Office 365 Advanced Threat Protection を構成する<br>-Microsoft Cloud App Security を構成する<br>-Azure Advanced Threat Protection を構成する<br>-Microsoft Defender Advanced Threat Protection を構成する 


## <a name="in-scope"></a>範囲内

このガイドの対象となるタスクは次のとおりです。
-   Azure Active Directory をセットアップする
-   Microsoft の脅威保護をセットアップする
    -   パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、完全ライセンスを使用します。
    -   ドメインを構成する
    -   Microsoft 365 E5 ライセンスを割り当てる
    -   ポータル内のセットアップウィザードの完了
-   ベストプラクティスに基づいてすべての Microsoft 脅威保護の柱を構成する
    -   Office 365 Advanced Threat Protection
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Advanced Threat Protection

## <a name="out-of-scope"></a>対象外

この展開ガイドの範囲外のものを以下に示します。

-   Microsoft の脅威保護と統合される可能性があるサードパーティ製のソリューションの構成
-   運用環境でのペネトレーションテスト

## <a name="next-step"></a>次のステップ
![フェーズ 1: 準備](../../media/prepare.png) <br>[フェーズ 1: 準備](prepare-mtpeval.md) 
<br> Microsoft の脅威保護の試用ラボまたはパイロット環境の準備

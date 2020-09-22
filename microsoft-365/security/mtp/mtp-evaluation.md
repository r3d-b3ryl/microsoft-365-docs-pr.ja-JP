---
title: Microsoft Threat Protection を評価する
description: Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップして、デバイス、id、データ、およびアプリケーションを保護するために設計された調整脅威保護ソリューションが組織にどのように役立つかを確認します。
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 202a5900dedece865f1aa328735477293a8a19c0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201773"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Microsoft の脅威保護の試用ラボまたはパイロット環境を作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

この試用版またはパイロット環境を作成する目的は、Microsoft の脅威保護に関する総合的かつ統合されたインテリジェントな機能を示しています。これは、組織で使用できる検出、防止、調査、および応答に関するものです。 

このガイドでは、推奨される展開パスに基づいて Microsoft の脅威保護評価を開始する手順について説明します。 目標は、完全なライセンスを使用している場合に、試用版のアカウントを使用するとき、または運用環境で試験環境で統合された Microsoft Threat Protection サービスをセットアップするのに役立ちます。 の結果は、組織内のセキュリティソリューションの意思決定者にセキュリティ操作のユースケースを提示するのに役立ちます。 攻撃のシミュレーションを実行し、結果に問題がなければ、組織内の Microsoft テクニカルセールス担当者または専門家と協力して、組織内で operationalize it を完全に展開し、それを確認することができます。 

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

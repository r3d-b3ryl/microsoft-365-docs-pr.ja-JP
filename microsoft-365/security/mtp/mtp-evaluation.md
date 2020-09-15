---
title: Microsoft Threat Protection を評価する
description: Microsoft の脅威保護の試用ラボ環境をセットアップして、デバイス、id、データ、およびアプリケーションを保護するために設計された調整脅威保護ソリューションが組織にどのように役立つかを確認します。
keywords: Microsoft Threat Protection の試用版、microsoft の脅威保護の評価、microsoft の脅威保護評価ラボ、サイバーセキュリティ、高度な脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649963"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Microsoft の脅威保護のテスト環境を作成する 

**適用対象:**
- Microsoft Threat Protection

この試用版ラボ環境を作成する目的は、組織で使用できる検出、防止、調査、および応答に関する Microsoft の脅威保護の総合的かつ統合化された機能を説明することです。 

このガイドでは、推奨される展開パスに基づいて Microsoft の脅威保護評価を開始する手順について説明します。 目標は、組織のセキュリティソリューション意思決定者に提示する際に、統合された Microsoft Threat Protection サービスをラボ環境で設定したり、概念実証 (POC) として設定したりするのに役立ちます。 攻撃のシミュレーション、自動化された調査、および応答を実行し、結果に満足している場合は、Microsoft テクニカルセールス担当者または組織内の専門家と協力して運用環境に展開できます。 

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
| ![フェーズ 1: 準備](../../media/prepare.png)<br>[フェーズ 1: 準備](prepare-mtpeval.md)| マイクロソフトの脅威保護を試用ラボ環境に展開するときに考慮する必要があることについて説明します。 <br><br>-関係者と承認 <br> -環境に関する考慮事項 <br>-アクセス <br>-Azure Active Directory のセットアップ <br> -構成の順序
|  ![フェーズ 2: セットアップ](../../media/setup.png) <br>[フェーズ 2: セットアップ](setup-mtpeval.md)|  最初の手順を実行して、microsoft 365 セキュリティセンターにアクセスし、Microsoft の脅威保護のテスト環境をセットアップします。 次のようなガイドが表示されます。<br><br>-Microsoft 365 E5 試用版にサインアップする <br>  -ドメインの構成<br>-Microsoft 365 E5 ライセンスを割り当てる<br>-ポータルのセットアップウィザードを完了します。|
|  ![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png) <br>[フェーズ 3: 構成 & オンボード](config-mtpeval.md) | Microsoft の各脅威保護の柱とオンボードエンドポイントを構成します。 次のようなガイドが表示されます。<br><br>-Office 365 Advanced Threat Protection を構成する<br>-Microsoft Cloud App Security を構成する<br>-Azure Advanced Threat Protection を構成する<br>-Microsoft Defender Advanced Threat Protection を構成する 


## <a name="in-scope"></a>範囲内

この試用版ラボ環境ガイドの範囲は次のとおりです。
-   Azure Active Directory をセットアップする
-   Microsoft の脅威保護をセットアップする
    -   Microsoft 365 E5 試用版にサインアップする
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

-   Microsoft Defender ATP と統合される可能性があるサードパーティ製のソリューションの構成
-   運用環境でのペネトレーションテスト

## <a name="next-step"></a>次の手順
![フェーズ 1: 準備](../../media/prepare.png) <br>[フェーズ 1: 準備](prepare-mtpeval.md) 
<br> Microsoft の脅威保護評価ラボ環境の準備

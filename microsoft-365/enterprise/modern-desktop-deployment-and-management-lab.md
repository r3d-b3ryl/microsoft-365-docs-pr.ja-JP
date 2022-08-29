---
title: Windows と Office 365 展開ラボ キット
f1.keywords:
- NOCSH
ms.author: aaroncz
author: cdmm12
manager: dougeby
ms.reviewer: alainme
ms.date: 05/11/2022
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows および Office 展開ラボ キットにアクセスする場所について説明します。
ms.openlocfilehash: fcb0b24480c61dcd5d3856aa800d6a30566d3b02
ms.sourcegitcommit: 2d1302a6165b83cbbc8c2df2c608d43b6b0498b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67433680"
---
# <a name="windows-and-office-365-deployment-lab-kit"></a>Windows と Office 365 展開ラボ キット

Windows と Office 365 の展開ラボ キットは、Windows 10 EnterpriseまたはWindows 11 EnterpriseおよびMicrosoft 365 Apps for enterpriseを実行するデスクトップの展開と管理を計画、テスト、検証するのに役立ちます。 このキットのラボでは、Microsoft Endpoint Configuration Manager、OneDrive、Windows Autopilot などを使用しています。 このキットは、デスクトップ アップグレードの準備をしている組織に強くお勧めします。 分離された環境として、ラボは、デプロイ ツールの更新プログラムの探索や、デプロイ関連の自動化のテストにも最適です。

ラボには、次の 2 つのバージョンが無料でダウンロードできます。  

|Windows 10 ラボ|Windows 11 ラボ|
|---|---|
|[Win 10 ラボ環境](https://download.microsoft.com/download/8/5/e/85e007b0-1f3e-460c-bd0a-5a8c6ec490b5/Win10_21H2_lab.zip)|[Win 11 ラボ環境](https://download.microsoft.com/download/5/0/b/50bbe36a-9291-4339-9dcc-2a444fcd1659/Microsoft365DeviceLabKit.zip)|
|[Win 10 ラボ ガイド](https://download.microsoft.com/download/b/d/4/bd4f430b-8cd1-4a07-97b1-c32100fce7ae/Win_10_21H2_lab_guides.zip)|[Win 11 ラボ ガイド](https://download.microsoft.com/download/5/0/b/50bbe36a-9291-4339-9dcc-2a444fcd1659/Win11_SetUp_Guide_08.05.zip)|

## <a name="a-complete-lab-environment"></a>完全なラボ環境

ラボには、ドメイン参加デスクトップ クライアント、ドメイン コントローラー、インターネット ゲートウェイ、完全に構成されたConfiguration Manager インスタンスなど、自動的にプロビジョニングされた仮想ラボ環境が用意されています。 ラボには、次の製品の評価バージョンが含まれています。

|Windows 10 ラボ|Windows 11 ラボ|
|---|---|
|Windows 10 Enterpriseバージョン 21H2|Windows 11 Enterprise|
|Microsoft Endpoint Configuration Manager、バージョン 2103|Microsoft Endpoint Configuration Manager バージョン 2203|
|Windows 10 用 Windows アセスメント & デプロイメント キット|windows Assessment and Deployment Kit for Windows 11|
|Windows Server 2019|Windows Server 2022|

ラボは、次の目的で試用版に接続するようにも設計されています。

- Microsoft 365 E5
- Microsoft 365 Apps for enterprise
- Enterprise Mobility + Security (EMS) を使用したOffice 365 E5

## <a name="step-by-step-labs"></a>ステップ バイ ステップ ラボ

詳細なラボのガイドにより、複数の展開および管理シナリオを体験できます。 最新バージョンの Intune と Configuration Manager 用にラボは更新されました。 注: ラボの新しいWindows 11 バージョンが利用可能になりました。 ラボ ガイドには、次のシナリオが含まれます。

### <a name="plan-and-prepare-infrastructure"></a>インフラストラクチャの計画と準備

- Cloud Management Gateway
- テナントのアタッチと共同管理
- エンドポイントの分析
- 更新プログラムの配信を最適化する

### <a name="deploy-windows"></a>Windows を展開する

- Configuration Managerの OS 展開タスク シーケンス
- Windows Autopilot

### <a name="service-windows"></a>サービス Windows

- グループ ポリシーを使用した Windows のサービス
- Microsoft Intuneを使用した Windows のサービス
- Configuration Managerを使用した Windows のサービス

### <a name="deploy-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise を展開する

- クラウドマネージドデプロイ
- ローカルで管理されたデプロイ
- AD に参加していないデバイスでのMicrosoft 365 Apps for enterprise展開
- Configuration Managerを使用したエンタープライズマネージドデプロイ
- Microsoft Intuneを使用したエンタープライズマネージドデプロイ
- Configuration Managerを使用したサービス Microsoft 365 Apps for enterprise
- Intuneを使用したサービス Microsoft 365 Apps for enterprise
- Microsoft Intuneを使用した LOB の展開と管理
- Microsoft Teams を展開する
- 割り当てフィルター

### <a name="managing-microsoft-edge"></a>Microsoft Edge の管理

- Edge の展開と更新
- IE モード
- エンタープライズの新しいタブ ページをセットアップする

### <a name="security-and-compliance"></a>セキュリティとコンプライアンス

- BitLocker
- Microsoft Defender ウイルス対策
- Windows Hello for Business
- Windows Defender Credential Guard       
- Microsoft Defender Application Guard     
- Windows Defender Exploit Guard             
- Windows Defender Application Control   
- Microsoft Defender for Endpoint 


> [!NOTE]
> ブロードバンド インターネット接続を使用してこのコンテンツをダウンロードし、自動プロビジョニングに約 30 分かかります。 ラボ環境では、少なくとも 16 GB の使用可能なメモリと 150 GB の空きディスク領域が必要です。 最適なパフォーマンスを実現するために、32 GB の使用可能なメモリと 300 GB の空き領域が推奨されます。 Windows クライアント仮想マシンの有効期限は、ラボのアクティブ化から 90 日後です。 ラボの新しいバージョンは、2022 年 11 月 5 日以前に公開されます。 

## <a name="additional-guidance"></a>追加のガイダンス

- [Windows クライアントの展開リソースとドキュメント](/windows/deployment)
- [Microsoft Mechanics による「デスクトップの展開」シリーズのビデオ](https://www.aka.ms/watchhowtoshift)
- [Microsoft Endpoint Configuration Manager OS の展開](/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)
- [Microsoft 365 Apps の展開ガイド](/deployoffice/deployment-guide-microsoft-365-apps)
- [Intune が会社のためにできることとは。](/intune/get-started-evaluation)

## <a name="related-resources"></a>関連リソース

- [Microsoft 365 の概要](https://www.microsoft.com/microsoft-365/default.aspx)
- [Microsoft 365 for business](https://products.office.com/business/office)
- [Enterprise Mobility + Security の概要](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
- [Windows for Business](https://www.microsoft.com/windows/business)

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
description: WindowsとOffice展開ラボ キットにアクセスする場所について説明します。
ms.openlocfilehash: e90a52a23c6c79a3293d381c0503480abc90c2d7
ms.sourcegitcommit: 37111bc0c5a6cc4690f7144a019bbff11d44858f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65463167"
---
# <a name="windows-and-office-365-deployment-lab-kit"></a>Windows と Office 365 展開ラボ キット

WindowsとOffice 365の展開ラボ キットは、Windows 10 EnterpriseまたはWindows 11 Enterpriseを実行するデスクトップの展開と管理を計画、テスト、検証するのに役立ちます。Microsoft 365 Apps for enterprise。 キット内のラボでは、Microsoft Endpoint Configuration Manager、OneDrive、Windows Autopilot などを使用します。 このキットは、デスクトップ アップグレードの準備をしている組織に強くお勧めします。 分離された環境として、ラボは、デプロイ ツールの更新プログラムの探索や、デプロイ関連の自動化のテストにも最適です。

ラボには、次の 2 つのバージョンが無料でダウンロードできます。  

|Windows 10 ラボ|Windows 11 ラボ|
|---|---|
|[Win 10 ラボ環境](https://download.microsoft.com/download/3/3/a/33a3c7d7-b393-4f78-9b90-2d5eb7fd98e8/Win10_21H1_lab.zip)|[Win 11 ラボ環境](https://download.microsoft.com/download/9/d/9/9d9e278e-a1ea-4704-85e1-cb24f3806f45/Win11_Lab_05.09.zip)|
|[Win 10 ラボ ガイド](https://download.microsoft.com/download/2/9/9/29952cdb-b98d-4f9b-9d6e-9fb49644b0a0/Win10_21H1_Lab_05.12.zip)|[Win 11 ラボ ガイド](https://download.microsoft.com/download/9/d/9/9d9e278e-a1ea-4704-85e1-cb24f3806f45/Win11_Lab_Guides_05.09.zip)|

## <a name="a-complete-lab-environment"></a>完全なラボ環境

ラボには、ドメイン参加デスクトップ クライアント、ドメイン コントローラー、インターネット ゲートウェイ、完全に構成されたConfiguration Manager インスタンスなど、自動的にプロビジョニングされた仮想ラボ環境が用意されています。 ラボには、次の製品の評価バージョンが含まれています。

|Windows 10 ラボ|Windows 11 ラボ|
|---|---|
|Windows 10 Enterpriseバージョン 21H1|Windows 11 Enterprise|
|Microsoft Endpoint Configuration Managerバージョン 2203|Microsoft Endpoint Configuration Managerバージョン 2203|
|Windows 10 用 Windows アセスメント & デプロイメント キット|Windows 11のWindows評価と展開キット|
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

### <a name="deploy-windows"></a>Windowsのデプロイ

- Configuration Managerの OS 展開タスク シーケンス
- Windows Autopilot

### <a name="service-windows"></a>サービス Windows

- グループ ポリシーを使用したサービス Windows
- Microsoft Intuneを使用したサービス Windows
- Configuration Managerを使用したWindowsのサービス

### <a name="deploy-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise を展開する

- クラウドマネージドデプロイ
- ローカルで管理されたデプロイ
- AD に参加していないデバイスでのMicrosoft 365 Apps for enterprise展開
- Configuration Managerを使用したマネージド デプロイのEnterprise
- Microsoft Intuneを使用したマネージド デプロイのEnterprise
- Configuration Managerを使用したサービス Microsoft 365 Apps for enterprise
- Intuneを使用したサービス Microsoft 365 Apps for enterprise
- Microsoft Intuneを使用した LOB の展開と管理
- Microsoft Teamsのデプロイ
- 割り当てフィルター

### <a name="managing-microsoft-edge"></a>Microsoft Edgeの管理

- Edge の展開と更新
- IE モード
- 新しいタブ ページEnterpriseセットアップする

### <a name="security-and-compliance"></a>セキュリティとコンプライアンス

- BitLocker
- Microsoft Defender ウイルス対策
- Windows Hello for Business

> [!NOTE]
> ブロードバンド インターネット接続を使用してこのコンテンツをダウンロードし、自動プロビジョニングに約 30 分かかります。 ラボ環境では、少なくとも 16 GB の使用可能なメモリと 150 GB の空きディスク領域が必要です。 最適なパフォーマンスを実現するために、32 GB の使用可能なメモリと 300 GB の空き領域が推奨されます。 Windows 10 ラボの有効期限は 2022 年 8 月 11 日です。 Windows 11 ラボの有効期限は 2022 年 8 月 7 日です。 新しいバージョンは、有効期限が切れる前に発行されます。

## <a name="additional-guidance"></a>追加のガイダンス

- [Windows クライアントデプロイリソースとドキュメント](/windows/deployment)
- [Microsoft Mechanics による「デスクトップの展開」シリーズのビデオ](https://www.aka.ms/watchhowtoshift)
- [Microsoft Endpoint Configuration Manager OS の展開](/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)
- [Microsoft 365 Apps の展開ガイド](/deployoffice/deployment-guide-microsoft-365-apps)
- [Intune が会社のためにできることとは。](/intune/get-started-evaluation)

## <a name="related-resources"></a>関連リソース

- [Microsoft 365 の概要](https://www.microsoft.com/microsoft-365/default.aspx)
- [Microsoft 365 for business](https://products.office.com/business/office)
- [Enterprise Mobility + Security の概要](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
- [ビジネス向けのWindows](https://www.microsoft.com/windows/business)

---
title: Windows と Office 展開ラボ キット
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows および Office 展開ラボ キットと、その入手方法について説明します。
ms.openlocfilehash: 86bdf37ca56c5779042ee78be091dd14ee63b80e
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "34814548"
---
# <a name="windows-and-office-deployment-lab-kit"></a>Windows と Office 展開ラボ キット

ダウンロード可能なこれらのハンズオン ラボでは、Windows 10 や Office 365 の展開と、展開後の構成や管理に関する考慮事項を主に扱います。このトレーニングは、Windows 7 のサポート終了に備えようとしている組織に特にお勧めしますが、Windows 10 と Office 365 Plus または Office 2019 を現在使用中のユーザーにも適用されます。このトレーニングには、Windows 10、Office 365 ProPlus、Enterprise Mobility + Security、および関連する製品やサービスのガイドが含まれます。

これらのラボは、Windows 10 Enterprise および Office 365 ProPlus を実行するデスクトップの展開と管理を計画、テスト、検証するために設計されています。 このラボでは、デスクトップ展開の円環に記載されている手順とツールをカバーします。これは、System Center Configuration Manager、Windows Analytics、Office カスタマイズ ツール、OneDrive、Windows Autopilot などにまたがります。

Windows 10 と Office 365 ProPlus での「[デスクトップ展開](http://www.aka.ms/howtoshift)」プロセスの一部として、展開ツールの更新プログラムの確認や展開関連の自動化をテストするとき、まず、セキュリティで保護されるか隔離されているラボ環境を構築するようにお勧めします。

ラボ キットは無料でダウンロードでき、試用版ソフトウェアを使用します。

### <a name="download-the-windows-and-office-deployment-lab-kithttpswwwmicrosoftcomevalcenterevaluate-lab-kit"></a>[**Windows と Office 展開ラボ キットのダウンロード**](https://www.microsoft.com/evalcenter/evaluate-lab-kit)

## <a name="a-complete-lab-environment"></a>**完全なラボ環境**

このラボでは、自動的にプロビジョニングされた仮想ラボ環境が提供されます。これには、ドメインに参加しているデスクトップ クライアント、ドメイン コントローラー、インターネット ゲートウェイ、および完全に構成された ConfigMgr インスタンスが含まれます。ラボには、次の製品の評価版が含まれています。

  - Windows 10 Enterprise、バージョン 1809
  - Windows 7
  - Office 365 ProPlus、バージョン 1901
  - System Center Configuration Manager、バージョン 1802
  - Windows 10 用 Windows アセスメント & デプロイメント キット、バージョン 1809
  - Microsoft Deployment Toolkit
  - Microsoft Application Virtualization (App-V) 5.1
  - Microsoft BitLocker Administration and Monitoring 2.5 SP1
  - Windows Server 2016
  - Microsoft SQL Server 2014

さらに、このラボは次の試用版に接続するように設計されています。

  - Microsoft 365 Enterprise E5

または
  - Office 365 Enterprise E5
  - Enterprise Mobility + Security

## <a name="step-by-step-labs"></a>**ステップ バイ ステップ ラボ**

詳細なラボのガイドにより、次のような複数の展開および管理シナリオを体験できます。

### <a name="device-and-app-readiness"></a>**デバイスとアプリの準備**

  - Windows Analytics
  - Internet Explorer のエンタープライズ モード、およびエンタープライズ モードのサイト リスト

### <a name="directory-and-network-readiness"></a>**ディレクトリとネットワークの準備**

  - Azure Active Directory と Microsoft 365 の基本的なセットアップ
  - 配信の最適化、ConfigMgr でのピア キャッシュ、LEDBAT を使用したネットワークの最適化
  - ConfigMgr と Microsoft Intune の共同管理
  - リモート アクセス (VPN)

### <a name="office-and-lob-app-delivery"></a>**Office と LOB アプリの配信**

  - System Center Configuration Manager を使用した Office 365 ProPlus の展開
  - Microsoft Intune を使用した Office 365 ProPlus の展開
  - Microsoft Intune を使用したアプリの展開と管理
  - ビジネス向け Microsoft Store を使用したアプリの展開とセルフ サービス インストール
  - デスクトップ ブリッジ アプリケーションの UWP への変換
  - Windows アプリ認定キット
  - IE のエンタープライズ モードを使用したブラウザーの互換性の問題解決

### <a name="user-file-and-settings-migration"></a>**ユーザー ファイルと設定の移行**

  - ConfigMgr と MDT における PC の更新および置換タスク シーケンスの一部としてのユーザー状態移行ツール
  - OneDrive の Known Folder Move
  - Enterprise State Roaming

### <a name="security-and-compliance"></a>**セキュリティと法令遵守**

  - BitLocker デバイス暗号化
  - Windows Defender ウイルス対策
  - Windows Hello for Business
  - 仮想化ベース セキュリティのイネーブラーとしての BIOS から UEFI への変換
  - Windows Defender Credential Guard
  - Windows Defender Application Guard
  - Windows Defender Exploit Guard
  - Windows Defender Application Control
  - Windows Defender Advanced Threat Protection

### <a name="os-deployment-and-feature-updates"></a>**OS の展開と機能の更新**

  - OS イメージの作成
  - ConfigMgr での OS 展開タスク シーケンス
      - ベア メタル
      - 更新
      - 置換
      - アップグレード
  - MDT での OS 展開タスク シーケンス
  - ConfigMgr でアップグレード タスク シーケンスを使用した機能更新
  - Windows Autopilot

### <a name="windows-and-office-servicing"></a>**Windows と Office サービス**

  - Configuration Manager を使用したソフトウェアの更新管理
  - Configuration Manager を使用した Office 365 ProPlus の更新管理
  - Microsoft Intune を使用した、Windows 10 に適用されるモバイル デバイスの管理

### <a name="download-the-windows-and-office-deployment-lab-kithttpsakamsmddlabsevalcenter"></a>[**Windows と Office 展開ラボ キットのダウンロード**](https://aka.ms/mddlabs_evalcenter)

*良好なダウンロード エクスペリエンスが得られるよう、このコンテンツのダウンロードには、広範な帯域幅をご使用ください。また、自動プロビジョニングには 30 から 45 分を見てください。ラボ環境には、少なくとも 16 GB の使用可能なメモリと 150 GB の空きディスク領域が必要です。最適なパフォーマンスを得るには、32 GB のメモリが使用可能であることが推奨されます。このラボは 2019 年 5 月 13 日で有効期限が切れますが、その前に新しいバージョンが公開される予定です。*

## <a name="additional-guidance"></a>**追加のガイダンス**

  - [デスクトップ展開センター](http://www.aka.ms/howtoshift)

  - [Microsoft Mechanics による「デスクトップの展開」シリーズのビデオ](http://www.aka.ms/watchhowtoshift)

  - 
  [System Center Configuration Manager の OS の展開](https://docs.microsoft.com/ja-JP/sccm/osd/understand/introduction-to-operating-system-deployment)

  - [<span class="underline">Windows 10 の展開計画</span>](https://docs.microsoft.com/windows/deployment/planning/index)

  - [<span class="underline">Office 365 ProPlus の展開ガイド</span>](https://docs.microsoft.com/deployoffice/deployment-guide-for-office-365-proplus)

  - [<span class="underline">Intune が会社のためにできることとは。</span>](https://docs.microsoft.com/intune/get-started-evaluation)

## <a name="related-resources"></a>**関連リソース**

  - [<span class="underline">Microsoft 365 の概要</span>](https://www.microsoft.com/microsoft-365/default.aspx)

  - [<span class="underline">Office 365 for business</span>](https://products.office.com/business/office)

  - [<span class="underline">Enterprise Mobility + Security の概要</span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

  - [<span class="underline">大企業向け Windows 10</span>](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)

  - [<span class="underline">中小企業向け Windows 10</span>](https://www.microsoft.com/WindowsForBusiness/windows-for-small-business)

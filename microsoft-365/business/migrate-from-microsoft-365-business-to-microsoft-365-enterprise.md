---
title: Microsoft 365 Business から Microsoft 365 E3 への移行
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: ビジネスを移行する方法については、Microsoft 365 Business PremiumからMicrosoft 365 E3。
ms.openlocfilehash: d3030518f7f4467c7b2e16897dc7b100764d9d5a36c50169b58f1adcd7bef209
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53837651"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Microsoft 365 Business Premium から Microsoft 365 E3 への移行

Microsoft 365 Business Premiumは、クラス最高のクラウドベースの生産性アプリと、簡単なデバイス管理とセキュリティを組み合わせて、従業員が最善の仕事を行うのに必要なすべてを持っています。 ただし、サブスクリプションを移行する必要がある場合Microsoft 365 Business Premium、Microsoft 365 E3。

たとえば、ビジネスが成長し、300 以上のライセンスが必要です (ところで、おめでとうございます)。

または、ビジネスには、クライアント アクセス ライセンス (CA) Microsoft 365 Apps for enterprise、Windows 10 Enterprise E3、Enterpriseなどのエンタープライズ機能が必要です。

アップグレードは簡単です。管理センターから [アップグレードを開始できます](../commerce/subscriptions/upgrade-to-different-plan.md)。 現在のサブスクリプションのすべてのデータと構成が維持されます。 新しい機能を利用する以外に、移行の準備には何もする必要もありません。その後は何も行いません。

> [!NOTE]
> また、最大 300 Microsoft 365 Business Premiumのサブスクリプションを使用し、300 Microsoft 365 E3を超えるサブスクリプションを取得できます。 ただし、Microsoft Defender for Office 365は、Microsoft 365 E3。 脅威の保護を継続するには、Office 365 ポリシーに対して Defender のスコープ内のすべてのユーザーがライセンスを取得Office 365追加する必要があります。

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>データとMicrosoft 365 Business Premiumの違Microsoft 365 Enterprise

次の表は、ユーザーとユーザーのMicrosoft 365 Business PremiumをMicrosoft 365 E3。

| 特徴    | Microsoft 365 Business Premium    | Microsoft 365 E3 |
|:-------|:-----|:-----|
| **社内**        | | |
| Windows 10    | Windows 10 Business  |     Windows 10 EnterpriseE3|
| Officeアプリ*    | [Microsoft 365 Apps for business](#office-365-business)    | Microsoft 365 Apps for Enterprise |
| **クラウド生産性アプリ**        | | |
| Exchange OnlineとOutlook    | メールボックスあたり 50 GB のストレージ制限と無制限のExchange Onlineアーカイブ    | メールボックスあたり 100 GB のストレージ制限と無制限のExchange Onlineアーカイブ |
| Teams    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| OneDrive for Business    | ユーザーあたり 1 TB のストレージ制限    | 無制限 |
| Yammer, SharePoint, Planner, Stream    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| **脅威保護**        | | |
| 攻撃表面の縮小機能    | [この一覧を見る](#threat-protection) | Enterpriseのハードウェア ベースの分離の管理Microsoft Edge |
| Microsoft Defender for Office 365 プラン 1 | ![Microsoft 365 Business Premium](../media/check-mark.png)    | 含まれていませんが、追加できます |
| **ID 管理**        | | |
| ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービス パスワードリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード 書き戻し|     ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| クラウド アプリの検出、Azure AD Connect正常性    |     | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| Azure AD Office 365 アプリ シングル Sign-On (SSO): 1 ユーザーあたり 10 アプリ (ギャラリー SaaS アプリ (Salesforce など)* | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーション プロキシ経由のオンプレミス アプリと、アプリ統合テンプレートを使用したギャラリー以外Self-Serviceアプリ)    |     | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| **デバイスおよびアプリの管理**        | | |
| Microsoft Intune, Windows オートパイロット|     ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
|仮想デスクトップ アクセス (VDA)    |  |     ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
|Windows仮想デスクトップ (WVD)    | ![Microsoft 365 Business Premium](../media/check-mark.png) |     ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
|共有コンピューターのライセンス認証 (SCA)    | ![Microsoft 365 Business Premium](../media/check-mark.png) |     ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| Microsoft デスクトップ最適化パッケージ    | |     ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| **情報保護**        | | |
| Office 365データ損失防止、Azure Information Protection Plan 1    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| エンドポイント DLP のウィンドウ情報保護    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| **クライアント アクセス ライセンス (CAL 権限)**    | | |
| EnterpriseCAL スイート (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows権限管理)| |         ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| **コンプライアンス**        | | |
| 無制限のメール アーカイブ    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| コンプライアンス マネージャー    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| 電子情報開示    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| インプレイスホールドと訴訟ホールド    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
| メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データに含まれるMicrosoft 365 E3](../media/check-mark.png) |
||||

\* SaaS アプリへのアクセスが割り当てられているユーザーは、最大 10 のアプリへの SSO アクセスを取得できます。 管理者は SSO を構成し、さまざまな SaaS アプリへのユーザー アクセスを変更できますが、SSO アクセスは一度に 1 ユーザーあたり 10 アプリに対してしか許可されません。 すべてのOffice 365アプリは 1 つのアプリとしてカウントされます。

## <a name="migration"></a>移行

移行するには、パートナーと一緒に、Microsoft 365 Business Premiumサブスクリプションとライセンスを適切なサブスクリプションMicrosoft 365 E3に移動します。

次のセクションでは、移行後に行う必要がある変更、変更がある場合、および実行できる操作について説明します。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365の構成とデータ

移行する前に、現在のサブスクリプションまたはデータに変更を加える必要は、次のとおりです。

- サブスクリプションの構成 (名前DNS ドメインなど)。
- 多要素認証や条件付きアクセス ポリシーなどのユーザー アカウントとグループ アカウントと認証設定。
- 生産性向上サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。

これで、ユーザーは、メールボックスとフォルダー内のExchange OnlineをOneDrive for Businessできます。

10 以上のアプリでクラウド アプリの検出、Azure AD Connect正常性、SSO の使用を開始できます。

<a name="threat-protection"></a>
### <a name="threat-protection"></a>脅威に対する保護

Windows 10 Businessには、次の保護が含まれます。

- オペレーティング システムの起動プロセスの整合性の適用
- 機密性の高いオペレーティング コンポーネントの整合性の適用
- 高度な脆弱性とゼロデイの悪用の軽減策
- 評価ベースのネットワーク保護 (Microsoft Edge、Internet Explorer、および Chrome 用
- ホスト ベースのファイアウォール
- ランサムウェアの軽減策
- デバイスのハードウェア ベースの分離Microsoft Edge
- インテリジェント セキュリティ システムを使用したアプリケーション制御Graph
- デバイスコントロール (USB)
- Web ベースの脅威に対するネットワーク保護
- ホスト侵入防止ルール

Windows 10 EnterpriseE3 には、ハードウェア ベースの分離のエンタープライズ管理も含Microsoft Edge。

> [!NOTE]
> ユーザーは、Microsoft 365 E3保護を継続するために、Microsoft Defender のライセンスOffice 365必要があります。 すべての Defender のスコープ内のすべてのユーザーが、Office 365のライセンスを受け取る場合は、必ず追加の Defender を購入Office 365してください。

### <a name="device-management-with-intune"></a>Intune を使用したデバイス管理

移行する前に、現在の Intune 構成に変更を加える必要は一切ない。これには、登録済みデバイスとデバイスとアプリの設定が含まれます。

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premiumには、Windows 10 Business AutoPilot と一緒にインストールできるWindowsが含まれます。 ユーザー ライセンスに移行Microsoft 365 E3、各ユーザー ライセンスには E3 Windows 10 Enterpriseが含まれます。このライセンスには、自動パイロットとWindowsできます。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for business

デバイスMicrosoft 365 Apps for businessクライアントが自動的にデバイスの機能の使用を開始Microsoft 365 Apps for enterprise。 移行後、次のコマンドを使用できます。

- グループ ポリシーのサポート
- スプレッドシートの比較と照会
- ビジネス インテリジェンス

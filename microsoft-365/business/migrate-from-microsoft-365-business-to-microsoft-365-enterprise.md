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
description: ビジネスを Microsoft 365 Business Premium から Microsoft 365 E3 に移行する方法について説明します。
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164515"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Microsoft 365 Business Premium から Microsoft 365 E3 への移行

Microsoft 365 Business Premium には、クラス最高のクラウドベースの生産性アプリと、簡単なデバイス管理とセキュリティを組み合わせて、従業員が最善の作業を行える、小規模ビジネスに必要なすべてを備えています。 ただし、Microsoft 365 Business Premium サブスクリプションを Microsoft 365 E3 に移行する必要がある場合があります。 

たとえば、ビジネスが成長し、300 以上のライセンスが必要です (ところで、おめでとうございます)。

または、エンタープライズ向け Microsoft 365 Apps、Windows 10 Enterprise E3、エンタープライズ クライアント アクセス ライセンス (CAL) などのエンタープライズ機能が必要です。

アップグレードは簡単です。管理センターから [アップグレードを開始できます](../commerce/subscriptions/upgrade-to-different-plan.md)。 現在のサブスクリプションのすべてのデータと構成が維持されます。 新しい機能を利用する以外に、移行の準備には何もする必要もありません。その後は何も行いません。

>[!Note]
>また、最大 300 シートの Microsoft 365 Business Premium サブスクリプションを使用し、300 シートを超える場合は Microsoft 365 E3 サブスクリプションを取得できます。 ただし、Microsoft Defender for Office 365 は Microsoft 365 E3 には含まれません。 脅威の保護を継続するには、Office 365 ライセンスに対して Defender を追加して、Office 365 ポリシーの Defender のスコープ内のすべてのユーザーがライセンスを取得する必要があります。
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 Business Premium と Microsoft 365 Enterprise の違い

次の表に、Microsoft 365 Business Premium と Microsoft 365 E3 の違いを示します。

| 機能    | Microsoft 365 Business Premium のサポート    | Microsoft 365 E3 でのサポート | 
|:-------|:-----|:-----|
| **社内**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Officeアプリ*    | [Microsoft 365 Apps for business](#office-365-business)    | Microsoft 365 Apps for enterprise | 
| **クラウド生産性アプリ**        | | | 
| Exchange Online と Outlook    | メールボックスあたり 50 GB のストレージ制限と Exchange Online の無制限のアーカイブ    | メールボックスあたり 100 GB のストレージ制限と Exchange Online の無制限のアーカイブ | 
| Teams    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| OneDrive for Business    | ユーザーあたり 1 TB のストレージ制限    | 無制限 | 
| Yammer, SharePoint Online, Planner, Stream    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| **脅威の防止**        | | | 
| 攻撃表面の縮小機能    | [この一覧を見る](#threat-protection) | Microsoft Edge のハードウェア ベースの分離のエンタープライズ管理 | 
| Microsoft Defender for Office 365 プラン 1 | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | 含まれていませんが、追加できます | 
| **ID 管理**        | | | 
| ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービス パスワードリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード ライトバック|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| クラウド アプリの検出、Azure AD接続の正常性    |     | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| Azure AD Office 365 アプリ シングル Sign-On (SSO): 1 ユーザーあたり 10 アプリ (ギャラリー SaaS アプリ (Salesforce など)* | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーション プロキシ経由のオンプレミス アプリと、アプリ統合テンプレートを使用したギャラリー以外Self-Service)    |     | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| **デバイスおよびアプリの管理**        | | | 
| Microsoft Intune、Windows Autopilot|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
|仮想デスクトップ アクセス (VDA)    |  |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
|Windows 仮想デスクトップ (WVD)    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
|共有コンピューターのライセンス認証 (SCA)    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| Microsoft デスクトップ最適化パッケージ    | |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| **情報保護**        | | | 
| Office 365 データ損失防止、Azure Information Protection Plan 1    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| エンドポイント DLP のウィンドウ情報保護    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| **クライアント アクセス ライセンス (CAL 権限)**    | | |     
| Enterprise CAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management)| |         ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| **コンプライアンス**        | | | 
| 無制限のメール アーカイブ    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| コンプライアンス マネージャー    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| 電子情報開示    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| インプレイスホールドと訴訟ホールド    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
||||

\* SaaS アプリへのアクセスが割り当てられているユーザーは、最大 10 のアプリへの SSO アクセスを取得できます。 管理者は SSO を構成し、さまざまな SaaS アプリへのユーザー アクセスを変更できますが、SSO アクセスは一度に 1 ユーザーあたり 10 アプリに対してしか許可されません。 すべてのOffice 365 アプリは、1 つのアプリとしてカウントされます。

## <a name="migration"></a>移行

移行するには、パートナーと一緒に Microsoft 365 Business Premium サブスクリプションとライセンスを、そのライセンスを持つ適切な Microsoft 365 E3 サブスクリプションに移行します。

次のセクションでは、移行後に行う必要がある変更、変更がある場合、および実行できる操作について説明します。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 サブスクリプションの構成とデータ

移行する前に、現在のサブスクリプションまたはデータに変更を加える必要は、次のとおりです。

- サブスクリプションの構成 (名前DNS ドメインなど)。
- 多要素認証や条件付きアクセス ポリシーなどのユーザー アカウントとグループ アカウントと認証設定。
- 生産性サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。

これで、ユーザーは Exchange Online メールボックスと OneDrive for Business フォルダーで無制限のストレージを利用できます。

10 以上のアプリで、クラウド アプリの検出、Azure AD接続正常性、SSO の使用を開始できます。

<a name="threat-protection"></a>
### <a name="threat-protection"></a>脅威に対する保護

Windows 10 Business には、次の保護が含まれています。

- オペレーティング システムの起動プロセスの整合性の適用
- 機密性の高いオペレーティング コンポーネントの整合性の適用
- 高度な脆弱性とゼロデイの悪用の軽減策
- Microsoft Edge、Internet Explorer、および Chrome の評判ベースのネットワーク保護
- ホスト ベースのファイアウォール
- ランサムウェアの軽減策
- Microsoft Edge のハードウェア ベースの分離
- インテリジェント セキュリティ グラフによるアプリケーション制御
- デバイスコントロール (USB)
- Web ベースの脅威に対するネットワーク保護
- ホスト侵入防止ルール

Windows 10 Enterprise E3 には、Microsoft Edge のハードウェア ベースの分離のエンタープライズ管理も含まれています。

>[!Note]
>Microsoft 365 E3 に移行されたユーザーは、継続的な脅威保護のために、Office 365 ライセンスの Microsoft Defender が必要です。 Office 365 の警察の Defender のスコープ内のすべてのユーザーがライセンスを取得するには、Office 36 Office 5 ライセンスに対して追加の Defender を購入してください。 
>

### <a name="device-management-with-intune"></a>Intune を使用したデバイス管理

移行する前に、現在の Intune 構成に変更を加える必要は一切ない。これには、登録済みデバイスとデバイスとアプリの設定が含まれます。

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium には、Windows AutoPilot を使用してインストールできる Windows 10 Business が含まれています。 Microsoft 365 E3 に移行すると、各ユーザー ライセンスに Windows 10 Enterprise E3 が含まれます。Windows Autopilot を使用してインストールできます。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for business

デバイスにインストールされている Microsoft 365 Apps for Business クライアントは、Microsoft 365 Apps for enterprise の機能の使用を自動的に開始します。 移行後、次のコマンドを使用できます。

 - グループ ポリシーのサポート
 - スプレッドシートの比較と照会
 - ビジネス インテリジェンス


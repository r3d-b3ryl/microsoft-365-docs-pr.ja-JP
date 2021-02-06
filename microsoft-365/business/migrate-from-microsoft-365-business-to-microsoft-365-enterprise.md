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
description: Microsoft 365 Business Premium から Microsoft 365 E3 にビジネスを移行する方法について説明します。
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126203"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Microsoft 365 Business Premium から Microsoft 365 E3 への移行

Microsoft 365 Business Premium には、クラス最高のクラウドベースの生産性アプリと、シンプルなデバイス管理とセキュリティを組み合わせて、従業員が最善の仕事を行える、小規模ビジネスに必要なすべてが備えています。 ただし、場合によっては、Microsoft 365 Business Premium サブスクリプションを Microsoft 365 E3 に移行する必要があります。 

たとえば、ビジネスが成長し、300 以上のライセンスが必要になったとします (おめでとうございます)。

または、ビジネスには、Microsoft 365 Apps for enterprise、Windows 10 Enterprise E3、Enterprise Client Access Licenses (CALs) などのエンタープライズ機能が必要です。

アップグレードは簡単です。管理センターから [アップグレードを開始できます](../commerce/subscriptions/upgrade-to-different-plan.md)。 現在のサブスクリプションのすべてのデータと構成が維持されます。 新しい機能を利用する以外に、移行を準備するために行う必要は何もありません。その後は何も行う必要もありません。

>[!Note]
>また、最大 300 シートの Microsoft 365 Business Premium サブスクリプションを使用して、300 シートを超える Microsoft 365 E3 サブスクリプションを取得できます。 ただし、Microsoft Defender for Office 365 は Microsoft 365 E3 には含まれていません。 脅威の防止を継続するには、Office 365 のポリシーに対して Defender の範囲内のすべてのユーザーにライセンスが与Office 365 ライセンスを追加する必要があります。
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 Business Premium と Microsoft 365 Enterprise の相違点

次の表に、Microsoft 365 Business Premium と Microsoft 365 E3 の違いを示します。

| 機能    | Microsoft 365 Business Premium のサポート    | Microsoft 365 E3 のサポート | 
|:-------|:-----|:-----|
| **社内**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office アプリ*    | [Microsoft 365 Apps for business](#office-365-business)    | Microsoft 365 Apps for enterprise | 
| **クラウド生産性向上アプリ**        | | | 
| Exchange Online と Outlook    | メールボックスあたり 50 GB の記憶域制限と無制限の Exchange Online アーカイブ    | メールボックスあたり 100 GB の記憶域制限と無制限の Exchange Online アーカイブ | 
| Teams    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| OneDrive for Business    | ユーザーごとに 1 TB の記憶域制限    | 無制限 | 
| Yammer、SharePoint Online、Planner、Stream    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| MileIQ    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | | 
| **脅威保護**        | | | 
| 攻撃表面の縮小機能    | [この一覧を見る](#threat-protection) | Microsoft Edge のハードウェア ベースの分離のエンタープライズ管理 | 
| Defender for Office 365 プラン 1 | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | 含まれていませんが、追加可能 | 
| **ID 管理**        | | | 
| ハイブリッド Azure Active Directory (Azure AD) アカウント、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード書き戻しのセルフサービス によるパスワードのリセット|     ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| Cloud App Discovery、Azure AD Connect Health    |     | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| Azure AD Office 365 アプリ シングル Sign-On (SSO): ユーザーあたり 10 アプリ (Salesforce などのギャラリー SaaS アプリ)* | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーション プロキシ経由のオンプレミス アプリと、Self-Service アプリ統合テンプレートを使用する非ギャラリー アプリ)    |     | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| **デバイスおよびアプリの管理**        | | | 
| Microsoft Intune、Windows Autopilot|     ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
|仮想デスクトップ アクセス (VDA)    |  |     ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png) |     ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
|共有コンピューターのライセンス認証 (SCA)    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png) |     ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| Microsoft デスクトップ最適化パッケージ    | |     ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| **情報保護**        | | | 
| Office 365 データ損失防止、Azure Information Protection プラン 1    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| エンドポイント DLP のウィンドウ情報保護    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| **クライアント アクセス ライセンス (CAL 権限)**    | | |     
| Enterprise CAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management)| |         ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| **コンプライアンス**        | | | 
| 無制限の電子メール アーカイブ    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| コンプライアンス マネージャー    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| 電子情報開示    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| インホールドと訴訟ホールド    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
| メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー    | ![Microsoft 365 Business Premium に含まれています](../media/check-mark.png)    | ![Microsoft 365 E3 に付属](../media/check-mark.png) | 
||||

\* SaaS アプリへのアクセスが割り当てられているユーザーは、最大 10 のアプリに SSO アクセスできます。 管理者は SSO を構成し、異なる SaaS アプリへのユーザー アクセスを変更できますが、SSO アクセスは一度に 1 ユーザーあたり 10 アプリに対してしか許可されません。 すべての Office 365 アプリは、1 つのアプリとしてカウントされます。

## <a name="migration"></a>移行

移行するには、パートナーと一緒に Microsoft 365 Business Premium サブスクリプションとライセンスを、そのライセンスを持つ適切な Microsoft 365 E3 サブスクリプションに移行します。

次のセクションでは、加える必要がある変更がある場合、および移行後に実行できる操作について説明します。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 サブスクリプションの構成とデータ

移行する前に、現在のサブスクリプションやデータに変更を加える必要は一切行う必要がなされません。これには次の内容が含まれます。

- サブスクリプションの構成 (名前DNS ドメインなど)。
- ユーザーアカウントとグループ アカウント、および多要素認証や条件付きアクセス ポリシーなどの認証設定。
- 生産性サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。

ユーザーは、Exchange Online メールボックスと OneDrive for Business フォルダーに無制限のストレージを使用できます。

Cloud App Discovery、Azure AD Connect Health、SSO を 10 以上のアプリで使用できます。

>[!Note]
>Microsoft 365 E3 に移行されたユーザーは、MigratIQ を使用できなくなりました。
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>脅威保護

Windows 10 Business には、次の保護が含まれています。

- オペレーティング システムの起動プロセスの整合性の適用
- 機密性の高いオペレーティング コンポーネントの整合性の適用
- 高度な脆弱性とゼロデイ悪用の軽減策
- Microsoft Edge、Internet Explorer、Chrome の評判ベースのネットワーク保護
- ホストベースのファイアウォール
- ランサムウェアの軽減策
- Microsoft Edge のハードウェア ベースの分離
- インテリジェント セキュリティ グラフを利用したアプリケーション制御
- デバイスコントロール (USB)
- Web ベースの脅威に対するネットワーク保護
- ホスト侵入防止ルール

Windows 10 Enterprise E3 には、Microsoft Edge のハードウェア ベースの分離のエンタープライズ管理も含まれています。

>[!Note]
>Microsoft 365 E3 に移行したユーザーは、継続的な脅威保護のために、Office 365 ライセンスの Microsoft Defender が必要です。 Office 365 の Defender のスコープ内のすべてのユーザーがライセンスを取得するために、Office 365 ライセンスに対して追加の Defender を購入してください。 
>

### <a name="device-management-with-intune"></a>Intune を使用したデバイス管理

移行する前に、現在の Intune 構成 (登録済みデバイスとデバイスとアプリの設定を含む) に変更を加える必要はない。

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium には、Windows AutoPilot でインストールできる Windows 10 Business が含まれています。 Microsoft 365 E3 に移行する場合、各ユーザー ライセンスには Windows 10 Enterprise E3 が含まれています。Windows Autopilot でもインストールできます。

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for business

デバイスにインストールされている Microsoft 365 Apps for Business クライアントは、Microsoft 365 Apps for enterprise の機能の使用を自動的に開始します。 移行後、次の機能を使用できます。

 - グループ ポリシーのサポート
 - スプレッドシートの比較と照会
 - ビジネス インテリジェンス


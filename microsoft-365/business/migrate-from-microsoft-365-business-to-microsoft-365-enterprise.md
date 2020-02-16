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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business から Microsoft 365 E3 にビジネスを移行する方法について説明します。
ms.openlocfilehash: cd6b9b14e9bc1ed03635be12873fb90592efe527
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065324"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a>Microsoft 365 Business から Microsoft 365 E3 への移行

Microsoft 365 Business は、お客様の中小企業に必要なすべての機能を備えており、クラス最高のクラウドベースの生産性アプリとシンプルなデバイスの管理とセキュリティを組み合わせることにより、従業員が最高の作業を行うことができます。 ただし、場合によっては、Microsoft 365 Business サブスクリプションを Microsoft 365 E3 に移行する必要があります。 

たとえば、ビジネスの成長が増え、300個を超えるライセンスが必要になりました (ご利用おめでとうございます)。

また、ビジネスには、Office 365 ProPlus、Windows 10 Enterprise E3、エンタープライズクライアントアクセスライセンス (Cal) などのエンタープライズ機能が必要です。

アップグレードは簡単です。[管理センターから](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide)アップグレードを開始できます。 現在のサブスクリプションのすべてのデータと構成が保持されます。 移行を準備するために実行する必要はありません。その後は、新しい機能を利用する以外に何もする必要はありません。 

>[!Note]
>また、Microsoft 365 Business サブスクリプションを最大300の席で使用することもできます。また、Microsoft 365 E3 サブスクリプションを使用して、300を超える座席を購入することもできます。 ただし、Office 365 ATP は Microsoft 365 E3 には含まれていません。 引き続き脅威を保護するには、office 365 ATP のライセンスを追加して、Office 365 ATP ポリシーの範囲内のすべてのユーザーがライセンスを持つようにする必要があります。
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a>Microsoft 365 Business と Microsoft 365 Enterprise の相違点

次の表は、Microsoft 365 Business と Microsoft 365 E3 の違いを示しています。

| 機能   | Microsoft 365 Business でのサポート | Microsoft 365 E3 のサポート | 
|:-------|:-----|:-----|
| **社内**       | | | 
| Windows 10    | Windows 10 Business  |    Windows 10 Enterprise E3| 
| Office アプリ *  | [Office 365 Business](#office-365-business)   | Office 365 ProPlus | 
| **クラウド生産性アプリ**       | | | 
| Exchange Online および Outlook   | メールボックスごとに 50 GB の格納域の制限と無制限の Exchange Online アーカイブ   | メールボックスごとに 100 GB の格納域の制限と無制限の Exchange Online アーカイブ | 
| Teams | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| OneDrive for Business | ユーザーごとに 1 TB のストレージ制限   | 無制限 | 
| Yammer、SharePoint Online、Planner、Stream    | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| Outlook カスタマーマネージャー、ミル Eiq  | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | | 
| **脅威保護**     | | | 
| 攻撃対象領域の削減機能 | [このリストを表示する](#threat-protection) | Microsoft Edge のハードウェアベースの分離のエンタープライズ管理 | 
| Office 365 Advanced Threat Protection (ATP) プラン1 | ![Microsoft 365 Business に含まれている](../media/check-mark.png) | 含まれていませんが、に追加できます。 | 
| **ID 管理**       | | | 
| ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービスによるパスワードのリセット、Azure 多要素認証 (MFA)、条件付きアクセス、オンプレミス id のパスワードの書き戻し|    ![Microsoft 365 Business に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| Cloud App Discovery、Azure AD Connect Health  |   | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| Azure AD Office 365 apps シングルサインオン (SSO): ユーザーごとに10個のアプリ (Salesforce などのギャラリー SaaS アプリ) * | ![Microsoft 365 Business に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーションプロキシと、セルフサービスアプリ統合テンプレートを使用したギャラリー以外のアプリを使用したオンプレミスアプリ)  |   | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| **デバイスとアプリの管理**     | | | 
| Microsoft Intune、Windows 自動操縦|  ![Microsoft 365 Business に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|仮想デスクトップアクセス (VDA)   |  |    ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|Windows 仮想デスクトップ (WVD)  | ![Microsoft 365 Business に含まれている](../media/check-mark.png) |    ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|共有コンピューターのライセンス認証 (SCA)   | ![Microsoft 365 Business に含まれている](../media/check-mark.png) |    ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| Microsoft デスクトップ最適化パッケージ    | |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| **情報保護**        | | | 
| Office 365 データ損失防止、Azure Information Protection プラン1  | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| エンドポイント DLP のウィンドウ情報の保護    | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| **クライアントアクセスライセンス (CAL 権限)**    | | |   
| エンタープライズ CAL スイート (Exchange、SharePoint、Skype、Windows、Microsoft エンドポイント構成マネージャー、Windows Rights Management)| |       ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| **コンプライアンス**        | | | 
| 無制限のメールのアーカイブ | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| コンプライアンススコア/コンプライアンスマネージャー   | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| 電子情報開示    | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| インプレース保持と訴訟ホールド | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー  | ![Microsoft 365 Business に含まれている](../media/check-mark.png)  | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
||||

\*SaaS アプリへのアクセスが割り当てられているユーザーは、最大10個のアプリへの SSO アクセスを取得できます。 管理者は SSO を構成し、さまざまな SaaS アプリへのユーザーアクセスを変更できますが、SSO アクセスは、一度に1ユーザーあたり10個のアプリに対してのみ許可されます。 すべての Office 365 アプリは、1つのアプリとして数えられます。

## <a name="migration"></a>移行

移行するには、パートナーと協力して、Microsoft 365 Business のサブスクリプションとライセンスを適切な Microsoft 365 E3 サブスクリプションにライセンスで移行します。

次のセクションでは、移行後に行う必要のある変更点と、その変更について説明します。

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 サブスクリプションの構成とデータ

移行する前に、現在のサブスクリプションまたはデータを変更する必要はありません。次のようなものがあります。

- サブスクリプションの構成 (DNS ドメイン名など)。
- ユーザーおよびグループのアカウントと、複数要素の認証や条件付きアクセスポリシーなどの認証設定。
- プロダクティビティサービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。

ユーザーは、Exchange Online メールボックスおよび OneDrive for Business フォルダーで無制限のストレージを利用できるようになりました。

最大10個のアプリに対して、クラウドアプリの検出、Azure AD Connect の正常性、および SSO の使用を開始できます。

>[!Note]
>Microsoft 365 E3 に移行されたユーザーは、Outlook カスタマーマネージャーおよびミル Eiq を使用できなくなります。
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>脅威保護

Windows 10 Business には次のような保護が含まれています。

- オペレーティングシステムの起動プロセスの整合性の適用
- 機密性の高いオペレーティングコンポーネントの整合性の適用
- 高度な脆弱性およびゼロ日の悪用対策
- Microsoft Edge、Internet Explorer、および Chrome の評価ベースのネットワーク保護
- ホストベースのファイアウォール
- ランサムウェア対策
- Microsoft Edge のハードウェアベースの分離
- インテリジェントセキュリティグラフが提供するアプリケーションコントロール
- デバイスコントロール (USB)
- Web ベースの脅威に対するネットワーク保護
- ホスト侵入防止ルール

Windows 10 Enterprise E3 には、Microsoft Edge のハードウェアベースの分離のエンタープライズ管理も含まれています。

>[!Note]
>Microsoft 365 E3 に移行されるユーザーには、継続的な脅威保護のために Office 365 ATP ライセンスが必要になります。 Office 365 ATP ポリシーの範囲内のすべてのユーザーがライセンスを受けられるように、追加の Office 365 ATP ライセンスを購入してください。 
>

### <a name="device-management-with-intune"></a>Intune を使用したデバイス管理

移行前に現在の Intune 構成を変更する必要はありません。これには、登録されたデバイスとデバイスおよびアプリの設定が含まれます。

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business には Windows 10 Business が含まれており、Windows 自動操縦を使用してインストールできます。 Microsoft 365 E3 に移行する場合は、各ユーザーライセンスに Windows 10 Enterprise E3 が含まれており、Windows 自動操縦を使用してインストールすることもできます。

<a name="office-365-business"></a>
### <a name="office-365-business"></a>Office 365 Business

デバイスにインストールされた Office 365 ビジネスクライアントは、自動的に Office 365 ProPlus の機能を使用するようになります。 移行後、次のものを使用できるようになります。

 - グループポリシーを使用したボリュームライセンス認証
 - アプリテレメトリ
 - コントロールを更新する
 - スプレッドシートの比較と照会
 - ビジネス インテリジェンス


---
title: Office 365 E3 からの Microsoft 365 Business への移行
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Office 365 E3 から Microsoft 365 Business Premium にビジネスを移行する方法について説明します。
ms.openlocfilehash: eebf78c24ed4bfd1a4fc2d843f37aebbe3d35e31
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558260"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Office 365 E3 から Microsoft 365 Business Premium への移行 

Microsoft 365 Business Premium は、お客様の中小企業に必要なすべての機能を備えており、クラスを備えたクラウドベースの生産性向上アプリをシンプルなデバイス管理とセキュリティと組み合わせることができます。 現在、Office 365 E3 サブスクリプションを所有していて、従業員の数が300を超えていない場合は、追加のセキュリティ機能を使用するように Microsoft 365 Business Premium に切り替えることを検討してください。

移行は簡単です。最初にライセンスを切り替え、現在のサブスクリプションのすべてのデータとユーザー情報を保持します。 移行後に、Microsoft 365 Business Premium で追加された機能を設定する必要があります。

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Office 365 E3 と Microsoft 365 Business Premium の相違点

次の表に、Microsoft 365 Business Premium と Office 365 E3 の相違点を示します。

| 機能    | Microsoft 365 Business Premium でのサポート    | Office 365 E3 のサポート | 
|:-------|:-----|:-----|
| **社内**        | | | 
| Office アプリ<sup>1</sup>    | Microsoft 365 Apps for business    | Microsoft 365 Apps for enterprise | 
| **クラウド生産性アプリ**        | | | 
| Exchange Online および Outlook    | メールボックスごとに 50 GB の格納域の制限と無制限の Exchange Online アーカイブ    | メールボックスごとに 100 GB の格納域の制限と無制限の Exchange Online アーカイブ | 
| Teams    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Office 365 E3 に含まれている](../media/check-mark.png) | 
| OneDrive for Business    | ユーザーごとに 1 TB のストレージ制限    | 無制限 | 
| Yammer、SharePoint Online、Planner、Stream    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Office 365 E3 に含まれている](../media/check-mark.png) | 
| StaffHub    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Office 365 E3 に含まれている](../media/check-mark.png) | 
| Outlook カスタマーマネージャー、ミル Eiq    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | | 
| **脅威保護**        | | | 
| Office 用 Defender 365 プラン1 | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | 含まれていませんが、に追加できます。 | 
| **ID 管理**        | | | 
| ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービスによるパスワードのリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス id のパスワードの書き戻し|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    |  | 
| **デバイスとアプリの管理**        | | |
| Microsoft Intune、Windows 自動操縦|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    |  |
| 共有コンピューターのライセンス認証|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Office 365 E3 に含まれている](../media/check-mark.png)| 
| Win 7/8.1 Pro ライセンスから Windows 10 Pro へのアップグレード権限|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    || 
| **情報保護**        | | |
|Office 365 データ損失防止|    ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)|![Office 365 E3 に含まれている](../media/check-mark.png)|
|Azure Information Protection プラン1、Bitlocker 強制|![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)||
|Azure Information Protection プラン1、機密ラベル|![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)||
|**クライアントアクセスライセンス (CAL 権限)**|||
|エンタープライズ CAL スイート (Exchange、SharePoint、Skype)||![Office 365 E3 に含まれている](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 Business Premium 版の Office アプリには、グループポリシー、アプリテレメトリ、更新制御、スプレッドシートの比較と照会、またはビジネスインテリジェンスを使用したボリュームライセンス認証は含まれていません。

## <a name="migration"></a>移行

サブスクリプションを移行するには、「 [プランを手動で変更](../commerce/subscriptions/change-plans-manually.md) する」を参照してください。一部のユーザーのみを Microsoft 365 Business Premium に移行する場合は、手順を確認してください。 また、 [すべてのユーザーを自動的にアップグレード](../commerce/subscriptions/upgrade-to-different-plan.md)したり、パートナーと協力して、E3 サブスクリプションとライセンスを Microsoft 365 Business Premium サブスクリプションに移行したりすることもできます。
次のセクションでは、移行後に行う必要のある変更点について説明します。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 サブスクリプションの構成とデータ
移行前に、現在のサブスクリプションまたはデータを変更する必要はありません。次のものが含まれます。

- DNS レコードやドメイン名などのサブスクリプションの構成。
- ユーザーおよびグループのアカウントと、複数要素の認証や条件付きアクセスポリシーなどの認証設定。
- プロダクティビティサービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。
- Office アプリケーションは自動的に拡大または縮小されます。 Office 365 のモダンライセンスでは、ユーザーのライセンスの割り当てが72時間ごとに確認され、Office アプリケーションはユーザーサブスクリプションに一致するバージョンに変換されます。

### <a name="windows-10"></a>Windows 10

Windows Pro Creator の更新プログラムを適用していない場合は、windows pro Creator update [にアップグレード](upgrade-to-windows-pro-creators-update.md)してください。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>ユーザーのデバイスとファイルを保護するためのポリシーを設定する

> [!NOTE]
> Office 365 MDM ポリシーおよびデバイスをセットアップすると、これらのデバイスは Microsoft 365 管理センターの [ **デバイス** ] ページに一覧表示されます。 セットアップしたポリシーはすべて、 [Intune ポータル](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)の従来のポリシーの一覧に表示されます。

Microsoft 365 Business Premium にライセンスを割り当てたら、ユーザーのデバイスとファイルの保護を開始できます。

組織内のすべてのユーザーを Microsoft 365 Business Premium にアップグレードした場合は、ホームページにセットアップウィザードが表示され、 [セットアップウィザードの手順で [Microsoft 365 Business Premium](set-up.md) のセットアップ] を使用してファイルとモバイルデバイスを保護することができます。

[デバイス] ページでは、次の手順を実行することもできます。
  
1. 管理センターの左側のナビゲーションで、[ **デバイス** \> **ポリシー**] に移動します。
    
2. [ **デバイスポリシー** ] ページで、[ **追加**] を選択します。
    
3. [ **ポリシーの追加** ] ウィンドウで、ポリシーの名前を指定し、ドロップダウンから **ポリシーの種類** を選択します。 
    
     Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。 詳細については、次のリンクを参照してください。
    
  - [Android または iOS デバイスのアプリ保護設定を設定する](app-protection-settings-for-android-and-ios.md)
    
  - [Windows 10 デバイスのアプリケーション保護設定を設定する](protection-settings-for-windows-10-devices.md)
    
  - [Windows 10 Pc のデバイス保護設定を設定する](protection-settings-for-windows-10-pcs.md)
  
4. ポリシーを設定すると、従業員はデバイスをセットアップできるようになります。
    
  - Windows デバイスの手順については、「 [Microsoft 365 Business Premium ユーザー向けに windows デバイスをセットアップする](set-up-windows-devices.md) 」を参照してください。 
    
  - Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business Premium ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md) 」を参照してください。 
  
### <a name="mailbox-size"></a>メールボックスのサイズ

Microsoft 365 Business Premium では、Exchange Online プラン1を使用しているため、50 GB の記憶域の制限があります。 Microsoft 365 Business Premium に移行する際に、ユーザーのいずれかが 50 GB を超えるメールボックスストレージを超えている場合は、このユーザーを Exchange Online プラン2に割り当て、Exchange Online プラン1を削除することをお勧めします。両方を割り当てることはできません。


### <a name="threat-protection"></a>脅威保護

Microsoft 365 Business Premium に移行した後、Office 365 用の Defender がインストールされています。 概要については、「 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 」を参照してください。 セットアップするには、「セキュリティで保護された [リンクのセットアップ](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)」、「安全な [添付ファイルの設定](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)」、および「 [Office 365 の Defender でのフィッシング対策の設定](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)」を参照してください。

### <a name="sensitivity-labels"></a>秘密度ラベル

機密ラベルの使用を開始するには、機密ラベル [の概要](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) と、 [機密ラベルの作成と管理](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) に関するビデオを参照してください。

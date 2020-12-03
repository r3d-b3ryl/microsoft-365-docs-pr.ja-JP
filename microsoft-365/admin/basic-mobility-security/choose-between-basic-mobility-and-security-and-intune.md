---
title: 基本的なモビリティとセキュリティおよび Intune のどちらかを選択する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、Microsoft 365 プランに含まれています。
ms.openlocfilehash: 8724b3dccbdb5949190ceda4b804b9f1f2a5d4b2
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561497"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>基本的なモビリティとセキュリティまたは Intune のどちらかを選択する

Microsoft [Intune](https://docs.microsoft.com/mem/intune/)は、特定の microsoft 365 プランに含まれるスタンドアロン製品であり、基本的なモビリティとセキュリティは microsoft 365 プランの一部です。 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>基本的なモビリティとセキュリティおよび Intune の可用性
 
基本的なモビリティとセキュリティと Intune は、次の表に示すさまざまなプランに含まれています。

| 計画 | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 アプリ|必要|いいえ|
|Microsoft 365 Business Basic|必要|いいえ|
|Microsoft 365 Business Standard|必要|いいえ|
|Office 365 E1 |必要|いいえ|
|Office 365 E3 |必要|いいえ|
|Office 365 E5 |必要|いいえ|
|Microsoft 365 Business Premium |はい|必要|
|Microsoft 365 Firstline 3 |はい|必要|
|Microsoft 365 Enterprise E3 |はい|必要|
|Microsoft 365 Enterprise E5 |はい|必要|
|Microsoft 365 エデュケーション A1 |はい|必要|
|Microsoft 365 Education A3 |はい|必要|
|Microsoft 365 Education A5 |はい|はい|
|Microsoft Intune |いいえ|はい|
|Enterprise Mobility & Security E3 |いいえ|はい|
|Enterprise Mobility & Security E5 |いいえ|はい|

>[!NOTE]
>既に Microsoft Intune を使用している場合は、基本的なモビリティとセキュリティの使用を開始することはできません。

 詳細については、「 [Microsoft 365 および Office 365 プラットフォームサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)」を参照してください。 

## <a name="differences-in-capabilities"></a>機能の相違点

Microsoft Intune および組み込みの基本的なモビリティとセキュリティはどちらも、組織内のモバイルデバイスを管理する機能を備えていますが、次の表で説明する機能には大きな違いがあります。

>[!NOTE]
>*最初に基本的なモビリティとセキュリティを設定し、次に Microsoft Intune を追加することで*、同じ Microsoft 365 Business Standard 組織での Intune と基本的なモビリティおよびセキュリティの両方を使用して、ユーザーとモバイルデバイスを管理することができます。 これにより、基本的なモビリティとセキュリティ、または機能豊富な Intune ソリューションを選択することができます。 Intune の機能を有効にするために Intune ライセンスを割り当てます。

| 機能領域 | 機能のハイライト | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|デバイスの種類|さまざまな OS プラットフォームと主要な管理モードのバリエーションを管理します。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad OS|
|デバイスのポリシー準拠|デバイスレベルの PIN ロックや jailbreak の検出などのセキュリティポリシーを設定および管理します。 |Android 9 以降のデバイスの制限。 [詳細](capabilities.md)を参照してください。 |必要|
|デバイスコンプライアンスに基づく条件付きアクセス |準拠していないデバイスが、クラウドから会社の電子メールやデータにアクセスできないようにします。 |Windows 10 ではサポートされていません。<br/>Exchange Online、SharePoint Online、Outlook へのアクセスを制御することに制限されています。 |必要 |
|デバイス構成  |デバイスの設定を構成する (たとえば、カメラを無効にする)|デバイスのポリシー準拠|デバイスレベルの PIN ロックや jailbreak の検出などのセキュリティポリシーを設定および管理します。 |Android 9 以降のデバイスの制限。 [詳細](capabilities.md)を参照してください。 |必要|
 |設定の制限されたセット。 |必要|
|電子メール プロファイル  |デバイス上にネイティブの電子メールプロファイルをプロビジョニングします。 |はい|必要|
|WiFi プロファイル |デバイス上にネイティブ Wi-fi プロファイルをプロビジョニングします。 |いいえ|はい|
|VPN プロファイル |デバイス上にネイティブの VPN プロファイルをプロビジョニングします。 |いいえ|はい|
|MDM アプリケーション管理 |内部の基幹業務アプリとアプリストアをユーザーに展開します。 |いいえ|はい|
|MAM |ユーザーが Office mobile および基幹業務アプリを使用して企業情報に安全にアクセスできるようにします。これにより、コピー、切り取り、貼り付け、および名前を付けて保存のような操作を、企業データに対して承認されたアプリケーションにのみ制限することができます。 |いいえ|はい|
|Managed browser  |エッジアプリを使用して、より安全な web ブラウジングを有効にします。 |いいえ|はい|
|ゼロタッチ登録プログラム自動操縦) |企業が所有する多数のデバイスを登録し、ユーザーの設定を簡素化します。 |いいえ|はい|
|||

上記の表に記載されている機能に加えて、基本的な Mobility and Security and Intune には、インターネット経由でデバイスにコマンドを送信するリモート操作のセットが含まれています。 たとえば、個人データを保存しておくか (削除)、従業員のデバイスから Office アプリを削除するか、またはデバイスを出荷時の設定 (完全ワイプ) にリセットすると、従業員のデバイスから Office データを削除することができます。 

基本的なモビリティおよびセキュリティのリモートアクションには、廃棄、ワイプ、フルワイプがあります。 基本的なモビリティおよびセキュリティアクションの詳細については、「 [Basic mobility And security の機能](capabilities.md)」を参照してください。

Intune では、次の一連の操作を実行できます。

-   自動操縦のリセット (Windows のみ
-  [Bitlocker キーの回転](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  (Windows のみ)
-  [デバイスをワイプ、削除、または手動で登録を取り消します。](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [ライセンス認証](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   の無効化(iOS のみ)
-  [新しい開始](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  (Windows のみ)
- [フルスキャン](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  (Windows 10 のみ)
- [デバイス](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   を探す(iOS のみ)
- [失われたモード](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  (iOS のみ)-[クイックスキャン](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10 のみ)
- [Android のリモートコントロール](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [リモート ロック](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [デバイス名の変更](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [パスコード](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)の[再起動](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)をリセットする   (Windows のみ)
-  Windows Defender セキュリティインテリジェンスを更新する (Windows のみ)
-  Windows 10 PIN リセット (Windows のみ)
-  [カスタム通知](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   を送信する(Android、iOS、iPad OS)
-  [デバイスの同期](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Intune アクションの詳細については、「 [Microsoft intune のドキュメント](https://docs.microsoft.com/mem/intune/)」を参照してください。

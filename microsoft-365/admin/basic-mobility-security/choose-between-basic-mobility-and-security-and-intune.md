---
title: Basic Mobility and Security と Intune の選択
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
description: Basic Mobility and Security は、Microsoft 365 プランの一部です。
ms.openlocfilehash: cfd1a68c313d1a1335490e2b8d6938de192fe3f3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877094"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Basic Mobility and Security または Intune の中から選択する

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) は、特定の Microsoft 365 プランに含まれているスタンドアロン製品ですが、Basic Mobility and Security は Microsoft 365 プランの一部です。 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Basic Mobility and Security と Intune の可用性
 
Basic Mobility と Security と Intune の両方が、次の表で説明するさまざまなプランに含まれています。

| プラン | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 アプリ|はい|いいえ|
|Microsoft 365 Business Basic|はい|いいえ|
|Microsoft 365 Business Standard|はい|いいえ|
|Office 365 E1 |はい|いいえ|
|Office 365 E3 |はい|いいえ|
|Office 365 E5 |はい|いいえ|
|Microsoft 365 Business Premium |はい|はい|
|Microsoft 365 Firstline 3 |はい|はい|
|Microsoft 365 Enterprise E3 |はい|はい|
|Microsoft 365 Enterprise E5 |はい|はい|
|Microsoft 365 Education A1 |はい|はい|
|Microsoft 365 Education A3 |はい|はい|
|Microsoft 365 Education A5 |はい|はい|
|Microsoft Intune |いいえ|はい|
|Enterprise Mobility & Security E3 |いいえ|はい|
|Enterprise Mobility & Security E5 |いいえ|はい|

>[!NOTE]
>Microsoft Intune を既に使用している場合は、Basic Mobility and Security の使用を開始できません。

 詳細については [、Microsoft 365 および Office 365 プラットフォーム](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)サービスの説明を参照してください。 

## <a name="differences-in-capabilities"></a>機能の違い

Microsoft Intune と組み込みの Basic Mobility と Security の両方で、組織内のモバイル デバイスを管理することができますが、次の表で説明する機能には主な違いがあります。

>[!NOTE]
>最初に Basic *Mobility と Security* を設定し、次に Microsoft Intune を追加することで、同じ Microsoft 365 Business Standard 組織で Intune と Basic Mobility and Security の両方を使用して、ユーザーとそのモバイル デバイスを管理できます。 これにより、Basic Mobility and Security またはより豊富な機能を持つ Intune ソリューションを選択できます。 Intune の機能を有効にする Intune ライセンスを割り当てる。

| 機能領域 | 機能のハイライト | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|デバイスの種類|さまざまな OS プラットフォームと主要な管理モードのバリエーションの管理。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad OS|
|デバイスのポリシー準拠|デバイス レベルの PIN ロックや脱獄の検出など、セキュリティ ポリシーを設定および管理します。 |Android 9 以降のデバイスの制限事項。 詳細を [参照してください](capabilities.md)。 |はい|
|デバイスのコンプライアンスに基づく条件付きアクセス |準拠しないデバイスがクラウドから企業の電子メールとデータにアクセスできない。 |Windows 10 ではサポートされていません。<br/>Exchange Online、SharePoint Online、および Outlook へのアクセスの制御に限定されます。 |はい |
|デバイス構成  |デバイス設定を構成する (たとえば、カメラを無効にする)|制限付き設定のセット。|はい|
|デバイスのポリシー準拠  |デバイス レベルの PIN ロックや脱獄の検出など、セキュリティ ポリシーを設定および管理します。 |Android 9 以降のデバイスの制限事項。 詳細を [参照してください](capabilities.md)。 |はい|
|電子メール プロファイル  |デバイスでネイティブメール プロファイルをプロビジョニングします。 |はい|はい|
|WiFi プロファイル |デバイスでネイティブの WiFi プロファイルをプロビジョニングします。 |いいえ|はい|
|VPN プロファイル |デバイスでネイティブ VPN プロファイルをプロビジョニングします。 |いいえ|はい|
|基本的なモビリティとセキュリティのアプリケーション管理  |内部の業務アプリとアプリ ストアからユーザーに展開します。 |いいえ|はい|
|モバイル アプリケーション保護  |ユーザーが知っている Office モバイル アプリと業務アプリを使用して企業情報に安全にアクセスできる一方で、企業データに対して承認されたアプリにのみコピー、切り取り、貼り付け、保存などの操作を制限することで、データのセキュリティを確保できます。 デバイスが Basic Mobility and Security に登録されていない場合でも動作します。 「MAM ポリシーを使ったアプリ データの保護」をご覧ください。 |いいえ|はい|
|管理対象ブラウザー  |Edge アプリを使用して、より安全な Web 閲覧を有効にする。 |いいえ|はい|
|ゼロ タッチ登録プログラム Autopilot) |多数の企業所有のデバイスを登録し、ユーザーのセットアップを簡素化します。 |いいえ|はい|
|||

上の表に示した機能に加えて、Basic Mobility and Security と Intune の両方に、インターネットを使用してデバイスにコマンドを送信する一連のリモート操作が含まれています。 たとえば、従業員のデバイスから Office データを削除し、個人データを定置 (廃止) しながら削除したり、従業員のデバイスから Office アプリを削除 (ワイプ) したり、デバイスを出荷時の設定 (フル ワイプ) にリセットすることができます。 

基本的なモビリティとセキュリティのリモート操作には、リタイア、ワイプ、フル ワイプが含まれます。 Basic Mobility and Security アクションの詳細については、「Basic Mobility and [Security」の機能を参照してください](capabilities.md)。

Intune では、次の一連の操作を実行できます。

-   Autopilot のリセット (Windows のみ)
-  [Bitlocker キーの回転](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  (Windows のみ)
-  [デバイスのワイプ、リタイア、または手動での登録解除を使用する](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [アクティブ化のロックを無効にする](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)  (iOS のみ)
-  [新しいスタート](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  (Windows のみ)
- [フル スキャン](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  (Windows 10 のみ)
- [デバイスの検索](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)  (iOS のみ)
- [失われたモード](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  (iOS のみ)-[クイック スキャン](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10 のみ)
- [Android 用のリモート コントロール](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [リモート ロック](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [デバイスの名前を変更する](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [パスコードのリセット](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)[の再起動](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Windows のみ)
-  セキュリティ Windows Defender更新プログラム (Windows のみ)
-  Windows 10 PIN のリセット (Windows のみ)
-  [カスタム通知を送信する](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)  (Android、iOS、iPad OS)
-  [デバイスの同期](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Intune の操作について詳しくは [、Microsoft Intune のドキュメントをご覧ください](https://docs.microsoft.com/mem/intune/)。

---
title: 基本的なモビリティとセキュリティとIntuneの間で選択する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、Microsoft 365計画の一部です。
ms.openlocfilehash: 0c1c61181d7e8bd5eb0ee000e29285c32a454692
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64713847"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>基本的なモビリティとセキュリティまたはIntuneを選択する

[Microsoft Intune](/mem/intune/)は、特定のMicrosoft 365プランに含まれるスタンドアロン製品ですが、Basic Mobility and Security はMicrosoft 365 プランの一部です。

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>基本的なモビリティとセキュリティとIntuneの可用性

Basic Mobility と Security とIntuneの両方が、次の表に示すさまざまなプランに含まれています。

| 計画 | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 Apps|はい|いいえ|
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
|Enterprise モビリティ & セキュリティ E3 |いいえ|はい|
|Enterprise Mobility & Security E5 |いいえ|はい|

> [!NOTE]
> Microsoft Intuneを既に使用している場合は、Basic Mobility and Security の使用を開始できません。

 詳細については、[プラットフォーム サービスの説明のMicrosoft 365とOffice 365を](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)参照してください。

## <a name="differences-in-capabilities"></a>機能の違い

Microsoft Intuneと組み込みの Basic Mobility と Security はどちらも、組織内のモバイル デバイスを管理する機能を提供しますが、次の表に示す機能には主な違いがあります。

> [!NOTE]
> 同じMicrosoft 365 Business Standard組織でIntuneと Basic Mobility と Security の両方を使用してユーザーとそのモバイル デバイスを管理するには *、最初に Basic Mobility と Security を設定してから、Microsoft Intuneを追加します*。 これにより、基本的なモビリティとセキュリティ、またはより機能の豊富なIntune ソリューションを選択できます。 Intune機能を有効にするには、Intune ライセンスを割り当てます。

| 機能領域 | 機能のハイライト | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|デバイスの種類|さまざまな OS プラットフォームと主要な管理モードバリアントを管理する。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad OS|
|デバイスのコンプライアンス|デバイス レベルの PIN ロックや脱獄検出など、セキュリティ ポリシーを設定および管理します。 |Android デバイスの制限事項。 詳細を参照 [してください](capabilities.md)。 |はい|
|デバイスコンプライアンスに基づく条件付きアクセス |準拠していないデバイスがクラウドから企業の電子メールとデータにアクセスできないようにします。 |Windows 10ではサポートされていません。<br/>Exchange Online、SharePoint Online、Outlookへのアクセスの制御に限定されます。 |はい |
|デバイス構成  |デバイス設定の構成 (カメラの無効化など)|設定の制限付きセット。|はい|
|電子メール プロファイル  |デバイスにネイティブ電子メール プロファイルをプロビジョニングします。 |はい|はい|
|WiFi プロファイル |デバイスにネイティブ WiFi プロファイルをプロビジョニングします。 |いいえ|はい|
|VPN プロファイル |デバイスにネイティブ VPN プロファイルをプロビジョニングします。 |いいえ|はい|
|モバイル アプリケーション管理  |社内基幹業務アプリとアプリ ストアからユーザーにデプロイします。 |いいえ|はい|
|モバイル アプリケーション保護  |ユーザーが知っているOfficeモバイル アプリと基幹業務アプリを使用して企業情報に安全にアクセスできるようにします。一方、コピー、切り取り、貼り付け、保存などのアクションを企業データに対して承認されたアプリのみに制限することで、データのセキュリティを確保します。 デバイスが Basic Mobility and Security に登録されていない場合でも機能します。 MAM ポリシーを使用したアプリ データの保護に関する説明を参照してください。 |いいえ|はい|
|管理対象ブラウザー  |Edge アプリを使用して、より安全な Web 閲覧を有効にします。 |いいえ|はい|
|ゼロ タッチ登録プログラム (AutoPilot) |多数の企業所有のデバイスを登録し、ユーザーのセットアップを簡略化します。 |いいえ|はい|

上の表に示す機能に加えて、Basic Mobility and Security とIntuneには、インターネット経由でデバイスにコマンドを送信する一連のリモート アクションが含まれています。 たとえば、個人データを配置したまま従業員のデバイスからOfficeデータを削除 (退職) したり、従業員のデバイスからOfficeアプリを削除したり (ワイプ)、デバイスを出荷時の設定にリセットしたり (完全ワイプ) できます。

基本的なモビリティとセキュリティのリモート アクションには、廃止、ワイプ、フル ワイプが含まれます。 Basic Mobility と Security のアクションの詳細については、「 [Basic Mobility and Security の機能」を参照してください](capabilities.md)。

Intuneには、次の一連のアクションがあります。

- [Autopilot リセット](/mem/autopilot/windows-autopilot-reset) (Windows のみ)
- [Bitlocker キーの回復](https://support.microsoft.com/windows/finding-your-bitlocker-recovery-key-in-windows-6b71ad27-0b89-ea08-f143-056f5ab347d6) (Windowsのみ)
- [デバイスのワイプ、廃止、または手動での登録解除を使用する](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
- [アクティブ化ロック](/mem/intune/remote-actions/device-activation-lock-disable) を無効にする(iOS のみ)
- [新しいスタート](/mem/intune/remote-actions/device-fresh-start) (Windowsのみ)
- [フル スキャン](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) (Windows 10のみ)
- [デバイスを](/mem/intune/remote-actions/device-locate) 見つける(iOS のみ)
- [紛失モード](/mem/intune/remote-actions/device-lost-mode) (iOS のみ)- [クイック スキャン](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10のみ)
- [Android のリモート コントロール](/mem/intune/remote-actions/teamviewer-support)
- [リモート ロック](/mem/intune/remote-actions/device-remote-lock)
- [デバイスの名前の変更](/mem/intune/remote-actions/device-rename)
- [パスコード](/mem/intune/remote-actions/device-passcode-reset)[の再起動](/mem/intune/remote-actions/device-restart) をリセットする(Windowsのみ)
- [セキュリティ インテリジェンスWindows Defender更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)する (Windowsのみ)
- [Windows 10 PIN リセット](/windows/security/identity-protection/hello-for-business/hello-feature-pin-reset) (Windowsのみ)
- [カスタム通知](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device) を送信する(Android、iOS、iPad OS)
- [デバイスを同期する](/mem/intune/remote-actions/device-sync)

Intuneアクションの詳細については、[Microsoft Intuneドキュメントを参照してください](/mem/intune/)。

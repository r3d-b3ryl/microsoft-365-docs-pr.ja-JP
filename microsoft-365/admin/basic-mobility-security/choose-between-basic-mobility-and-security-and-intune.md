---
title: 基本モビリティとセキュリティと Intune の間で選択する
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
- AdminTemplateSet
search.appverid:
- MET150
description: 基本モビリティとセキュリティは、重要なMicrosoft 365です。
ms.openlocfilehash: 74b6aeb5b768dc668a66bcb8c82f6c8393219561
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176903"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>基本モビリティとセキュリティまたは Intune の間で選択する

[Microsoft Intune](/mem/intune/)は特定のプランに含まれるスタンドアロン製品Microsoft 365、Basic Mobility and Security は一部のサービス プランMicrosoft 365です。

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Basic Mobility and Security and Intune の可用性

基本モビリティとセキュリティと Intune の両方が、次の表に示すさまざまなプランに含まれています。

| 計画 | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 アプリ|はい|いいえ|
|Microsoft 365 Business Basic|はい|いいえ|
|Microsoft 365 Business Standard|はい|いいえ|
|Office 365 E1 |はい|いいえ|
|Office 365 E3 |はい|いいえ|
|Office 365 E5 |はい|いいえ|
|Microsoft 365 Business Premium |はい|はい|
|Microsoft 365Firstline 3 |はい|はい|
|Microsoft 365 Enterprise E3 |はい|はい|
|Microsoft 365 Enterprise E5 |はい|はい|
|Microsoft 365 EducationA1 |はい|はい|
|Microsoft 365 Education A3 |はい|はい|
|Microsoft 365 Education A5 |はい|はい|
|Microsoft Intune |いいえ|はい|
|Enterpriseモビリティ &セキュリティ E3 |いいえ|はい|
|Enterprise Mobility & Security E5 |いいえ|はい|

> [!NOTE]
> 基本モビリティとセキュリティの使用は、既に使用している場合はMicrosoft Intune。

 詳細については、「プラットフォーム[サービスのMicrosoft 365とOffice 365」を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。

## <a name="differences-in-capabilities"></a>機能の違い

Microsoft Intune組み込みの Basic Mobility and Security では、どちらも組織内のモバイル デバイスを管理できますが、次の表で説明する機能には主な違いがあります。

> [!NOTE]
> 同じ Microsoft 365 Business Standard 組織で Intune と Basic Mobility and Security の両方を使用してユーザーとそのモバイル デバイスを管理するには、まず Basic Mobility and Security をセットアップし、次に Microsoft Intune を *追加します*。 これにより、基本モビリティとセキュリティ、または機能が豊富な Intune ソリューションを選択できます。 Intune の機能を有効にするには、Intune ライセンスを割り当てる必要があります。

| 機能領域 | 機能のハイライト | 基本的なモビリティとセキュリティ | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|デバイスの種類|さまざまな OS プラットフォームと主要な管理モードのバリエーションを管理する。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad OS|
|デバイスのポリシー準拠|デバイス レベルの PIN ロックや脱獄の検出など、セキュリティ ポリシーを設定および管理します。 |Android 9 以降のデバイスの制限事項。 詳細を [参照してください](capabilities.md)。 |はい|
|デバイスのコンプライアンスに基づく条件付きアクセス |準拠しないデバイスがクラウドから企業の電子メールとデータにアクセスしなかからな |このページではWindows 10。<br/>オンライン、オンライン、およびExchange Online、SharePointへのアクセスを制御Outlook。 |はい |
|デバイス構成  |デバイス設定を構成する (たとえば、カメラを無効にする)|制限された設定のセット。|はい|
|電子メール プロファイル  |デバイスでネイティブメール プロファイルをプロビジョニングします。 |はい|はい|
|WiFi プロファイル |デバイスでネイティブ WiFi プロファイルをプロビジョニングします。 |いいえ|はい|
|VPN プロファイル |デバイスにネイティブ VPN プロファイルをプロビジョニングします。 |いいえ|はい|
|モバイル アプリケーション管理  |社内の業務用アプリとアプリ ストアからユーザーに展開します。 |いいえ|はい|
|モバイル アプリケーション保護  |ユーザーが知っている Office モバイル アプリや業務アプリを使用して企業情報に安全にアクセスできる一方で、コピー、カット、貼り付け、保存などのアクションを企業データに対して承認されたアプリにのみ制限することで、データのセキュリティを確保できます。 デバイスが Basic Mobility and Security に登録されていない場合でも動作します。 「MAM ポリシーを使用してアプリ データを保護する」を参照してください。 |いいえ|はい|
|管理されたブラウザー  |エッジ アプリを使用して、より安全な Web ブラウズを有効にする。 |いいえ|はい|
|ゼロ タッチ登録プログラム (AutoPilot) |多数の企業所有デバイスを登録し、ユーザーのセットアップを簡略化します。 |いいえ|はい|
|||

前の表に示す機能に加えて、Basic Mobility and Security と Intune には、インターネットを使用してデバイスにコマンドを送信する一連のリモート アクションが含まれています。 たとえば、従業員のデバイスから Office データを削除し、個人データを一定の場所に残す (退職)、従業員のデバイスから Office アプリを削除 (ワイプ)、またはデバイスを工場出荷時の設定 (フル ワイプ) にリセットできます。

基本的なモビリティとセキュリティのリモート アクションには、削除、ワイプ、フル ワイプが含まれます。 Basic Mobility and Security アクションの詳細については、「Basic Mobility and Security の機能 [」を参照してください](capabilities.md)。

Intune では、次の一連のアクションを実行できます。

-   自動パイロットのリセット (Windowsのみ)
-  [Bitlocker キーの回転](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  (Windowsのみ)
-  [デバイスのワイプ、削除、手動での登録解除を使用する](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [ライセンス認証 loc を無効にする](/mem/intune/remote-actions/device-activation-lock-disable)  (iOS のみ)
-  [新しい開始](/mem/intune/remote-actions/device-fresh-start)  (Windowsのみ)
- [フル スキャン](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  (Windows 10のみ)
- [デバイスの検索](/mem/intune/remote-actions/device-locate)  (iOS のみ)
- [紛失モード](/mem/intune/remote-actions/device-lost-mode)  (iOS のみ)-[クイック スキャン](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10のみ)
- [Android 用リモート コントロール](/mem/intune/remote-actions/teamviewer-support)
- [リモート ロック](/mem/intune/remote-actions/device-remote-lock)
- [デバイスの名前を変更する](/mem/intune/remote-actions/device-rename)
-  [パスコードのリセット](/mem/intune/remote-actions/device-passcode-reset)[再起動](/mem/intune/remote-actions/device-restart)   (Windowsのみ)
-  セキュリティ Windows Defenderの更新 (Windowsのみ)
-  Windows 10PIN のリセット (Windowsのみ)
-  [カスタム通知の送信](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)  (Android、iOS、iPad OS)
-  [デバイスの同期](/mem/intune/remote-actions/device-sync)

Intune アクションの詳細については、「ドキュメント」[をMicrosoft Intuneしてください](/mem/intune/)。

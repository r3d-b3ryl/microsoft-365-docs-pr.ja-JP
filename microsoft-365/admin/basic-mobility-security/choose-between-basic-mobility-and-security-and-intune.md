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
ms.openlocfilehash: df52d500c945275b62170ab16260f0c019340f73
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429928"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>基本的なモビリティとセキュリティおよび Intune のどちらかを選択する

Microsoft Intune は、特定の Microsoft 365 プランに含まれているスタンドアロン製品であり、基本的な Mobility & セキュリティは Microsoft 365 プランの一部です。 次の表に示すように、どちらもさまざまなプランに含まれています。

|**計画**|**基本的なモビリティとセキュリティ**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Microsoft 365 アプリ|必要|いいえ|
|Microsoft 365 Business Basic|必要|いいえ|
|Microsoft 365 Business Standard|必要|いいえ|
|Office 365 E1 |必要|いいえ|
|Office 365 E3 |必要|いいえ|
|Office 365 E5 |必要|いいえ|
|Microsoft 365 Business Premium |はい|はい|
|Microsoft 365 Firstline 3 |はい|はい|
|Microsoft 365 Enterprise E3 |はい|はい|
|Microsoft 365 Enterprise E5 |はい|はい|
|Microsoft 365 Eductation A1 |はい|はい|
|Microsoft 365 Education A3 |はい|はい|
|Microsoft 365 Education A5 |はい|はい|
|Microsoft Intune |いいえ|はい|
|Enterprise Mobility & Security E3 |いいえ|はい|
|Enterprise Mobility & Security E5 |いいえ|はい|

>[!NOTE]
>既に Microsoft Intune を使用している場合は、基本的なモビリティとセキュリティの使用を開始することはできません。

## <a name="differences-in-capabilities"></a>機能の相違点

Microsoft Intune および組み込みの基本的なモビリティとセキュリティはどちらも、組織内のモバイルデバイスを管理する機能を備えていますが、次の表で説明する機能には大きな違いがあります。

>[!NOTE]
>最初に基本的なモビリティとセキュリティを設定し、次に Microsoft Intune を追加することで、同じ Microsoft 365 Business Standard 組織での Intune と基本的なモビリティおよびセキュリティの両方を使用して、ユーザーとモバイルデバイスを管理することができます。 これにより、基本的なモビリティとセキュリティ、または機能豊富な Intune ソリューションを使用して、ユーザーのデバイスを管理するかどうかを選択できます。 モードでは、ライセンスの割り当てによって、デバイスが登録されているサービスが決まります。 Intune ライセンスを割り当てて、Intune 専用機能を有効にします。

|**機能領域**|**機能のハイライト**|**基本的なモビリティとセキュリティ**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|デバイスの種類|OS プラットフォームと主要な管理モードのバリエーションが異なります。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS<br/>iPad OS|
|デバイスのポリシー準拠|デバイスレベルの PIN ロックや jailbreak の検出などのセキュリティポリシーを設定および管理します。 |Android 9 以降のデバイスの制限。 詳細については、「 [基本的なモビリティとセキュリティの機能](capabilities.md)」を参照してください。|必要|
|デバイスコンプライアンスに基づく条件付きアクセス |準拠していないデバイスが、クラウドから会社の電子メールやデータにアクセスできないようにします。 |-Windows 10 ではサポートされていません。<br/>-Exchange Online、Sharepoint Online、および Outlook サービスへのアクセスを制御することに制限されています。 |いいえ|
|デバイス構成  |デバイスの設定を構成します (たとえば、カメラを無効にします)。 |設定の制限されたセット。詳細については、「 [基本的なモビリティとセキュリティの機能](capabilities.md)」を参照してください。 |必要|
|リモート操作  |インターネット経由でデバイスにコマンドを送信します。 たとえば、個人データを保存したまま、従業員のデバイスから Office データを削除します (廃止)。 |破棄<br/>ワイプ<br/>削除|-自動操縦リセット (Windows のみ)<br/>- [Bitlocker キーの回転](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  (Windows のみ)<br/>- [デリート](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [ライセンス認証](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   の無効化(iOS のみ)<br/>- [新しい開始](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  (Windows のみ)<br/>- [フルスキャン](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  (Windows 10 のみ)<br/>- [デバイス](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   を探す(iOS のみ)<br/>- [失われたモード](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  (iOS のみ)<br/>- [クイックスキャン](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10 のみ)<br/>- [Android のリモートコントロール](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [リモートロック](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [デバイス名の変更](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [パスコードのリセット](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [再起動](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)  (Windows のみ)<br/>- [削除](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-Windows Defender セキュリティインテリジェンスを更新する (Windows のみ)<br/>-Windows 10 PIN リセット (Windows のみ)<br/>- [ふき](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [カスタム通知](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   を送信する(Android、iOS、iPad OS)<br/>- [デバイスの同期](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|電子メール プロファイル  |デバイス上にネイティブの電子メールプロファイルをプロビジョニングします。 |はい|はい|
|WIFI プロファイル |デバイス上にネイティブ WI-FI プロファイルをプロビジョニングします。 |いいえ|はい|
|VPN プロファイル |デバイス上にネイティブの VPN プロファイルをプロビジョニングします。 |いいえ|はい|
|MDM アプリケーション管理  |内部の基幹業務アプリとアプリストアをユーザーに展開します。 |いいえ|はい|
|モバイルアプリケーションの保護  |ユーザーが自分が知っている Office mobile および基幹業務アプリを使用して企業情報に安全にアクセスできるようにする一方で、企業データに対して承認されたアプリに対してのみ、コピー、切り取り、貼り付け、および名前を付けて保存の操作を制限することによって、データのセキュリティを確保できます。 MDM にデバイスが登録されていない場合でも動作します。 「MAM policies を使用してアプリデータを保護する」を参照してください。 |いいえ|はい|
|Managed browser  |エッジアプリを使用して、より安全な web ブラウジングを有効にします。 |いいえ|はい|
|ゼロタッチ登録プログラム |企業が所有する多数のデバイスを登録し、ユーザーの設定を簡素化します。 |いいえ|はい|

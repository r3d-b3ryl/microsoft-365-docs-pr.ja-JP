---
title: 基本的なモビリティとセキュリティのトラブルシューティング
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 基本モビリティとセキュリティの問題を追跡するには、次の手順を実行します。
ms.openlocfilehash: 2ac25e36fced24e5b50e7e89d36dae3e842fda04
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400365"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>基本的なモビリティとセキュリティのトラブルシューティング

デバイスを Basic Mobility and Security に登録しようとするときに問題が発生している場合は、ここでの手順を試して問題を追跡してください。 一般的な手順で問題が解決しない場合は、デバイスの種類に関する特定の手順を含む、以降のセクションのいずれかを参照してください。

## <a name="steps-to-try-first"></a>最初に試す手順

開始するには、次の情報を確認します。

- デバイスが Intune などの別のモバイル デバイス管理プロバイダーに既に登録されていないか確認します。

- デバイスが正しい日付と時刻に設定されていることを確認します。

- デバイス上の別の WIFI または携帯電話ネットワークに切り替えます。

- Android デバイスまたは iOS デバイスの場合は、デバイス上の Intune ポータル サイトアプリをアンインストールして再インストールします。 

## <a name="ios-phone-or-tablet"></a>iOS スマートフォンまたはタブレット

- 必ず APNs 証明書をセットアップしてください。 詳細については、「 [iOS デバイス用の APNs 証明書を作成する」を参照してください](create-an-apns-certificate-for-ios-devices.md)。

- [ **設定** > **GeneralProfile** >  **(またはデバイスの管理)** で、管理プロファイルがインストールされていないか確認します。 その場合は、削除します。

- "デバイスの登録に失敗しました" というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、Exchange Online を含むライセンスがデバイスにサインインしているユーザーに割り当てられている必要があります。

- "Profile がインストールに失敗しました" というエラー メッセージが表示された場合は、次のいずれかを試してください。

    - Safari がデバイスの既定のブラウザーであり、Cookie が無効にされていないか確認します。

    - デバイスを再起動し、デバイスに移動 portal.manage.microsoft.com。 ユーザー ID とパスワードMicrosoft 365サインインし、手動でプロファイルのインストールを試みる。

## <a name="windows-rt"></a>Windows RT

- Basic Mobility and Security を使用するには、ドメインMicrosoft 365設定してください。 詳細については、「Set [up Basic Mobility and Security」を参照してください](set-up.md)。
    
- Join を選択するのではなく、ユーザーが  **[オン** にする] を選択している **必要があります**。

## <a name="windows-10-pc"></a>Windows 10 PC

- Basic Mobility and Security を使用するには、ドメインMicrosoft 365設定してください。 詳細については、「Set [up Basic Mobility and Security」を参照してください](set-up.md)。
    
- 必要な情報がないAzure Active Directory Premium、ユーザーが [デバイス管理] で [ **Enroll** ] を選択している場合は、選択 **Connect。**

## <a name="android-phone-or-tablet"></a>Android スマートフォンまたはタブレット

- デバイスが Android を実行している必要があります。

- Chrome が最新であり、既定のブラウザーとして設定されている必要があります。

- 「このデバイスを登録できなかった」というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、Exchange Online を含むライセンスがデバイスにサインインしているユーザーに割り当てられている必要があります。

- デバイスの通知領域を確認して、必要なエンド ユーザーアクションが保留中か確認し、保留中の場合はアクションを完了します。
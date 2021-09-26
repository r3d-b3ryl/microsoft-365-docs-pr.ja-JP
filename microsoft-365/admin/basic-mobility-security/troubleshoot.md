---
title: 基本的なモビリティとセキュリティのトラブルシューティング
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 基本モビリティとセキュリティの問題を追跡するには、次の手順を実行します。
ms.openlocfilehash: 533e2d60d3c23809bdfbf6dda5a64e43082c739e
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775110"
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

- 必ず APNs 証明書をセットアップしてください。 詳細については [、「iOS デバイス用の APNs 証明書を作成する」を参照してください](create-an-apns-certificate-for-ios-devices.md)。

-  **[設定** プロファイル (またはデバイスの管理) で、管理プロファイルがインストール   >  ****   >  **** されていないか確認します。 その場合は、削除します。

- "デバイスの登録に失敗しました" というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、Exchange Online を含むライセンスがデバイスにサインインしているユーザーに割り当てられている必要があります。

- "Profile がインストールに失敗しました" というエラー メッセージが表示された場合は、次のいずれかを試してください。

    - Safari がデバイスの既定のブラウザーであり、Cookie が無効にされていないか確認します。

    - デバイスを再起動し、デバイスに移動 portal.manage.microsoft.com。 ユーザー ID とパスワードMicrosoft 365サインインし、手動でプロファイルのインストールを試みる。

## <a name="windows-rt"></a>Windows RT

- Basic Mobility and Security を使用するには、ドメインMicrosoft 365設定してください。 詳細については、「Set [up Basic Mobility and Security 」を参照してください](set-up.md)。
    
- [参加] を選択するのではなく、ユーザーが **[オン** にする] を   選択している必要 **があります**。

## <a name="windows-10-pc"></a>Windows 10PC

- Basic Mobility and Security を使用するには、ドメインMicrosoft 365設定してください。 詳細については、「Set [up Basic Mobility and Security 」を参照してください](set-up.md)。
    
- この設定がないAzure Active Directory Premium、ユーザーが [デバイス管理にのみ登録する] **** を選択し、[デバイスの管理] を選択   Connect。 ****

## <a name="android-phone-or-tablet"></a>Android スマートフォンまたはタブレット

- デバイスが Android 4.4 以降を実行している必要があります。

- Chrome が最新であり、既定のブラウザーとして設定されている必要があります。

- 「このデバイスを登録できなかった」というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、Exchange Online を含むライセンスがデバイスにサインインしているユーザーに割り当てられている必要があります。

- デバイスの通知領域を確認して、必要なエンド ユーザーアクションが保留中か確認し、保留中の場合はアクションを完了します。
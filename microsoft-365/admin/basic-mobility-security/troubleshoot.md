---
title: Basic Mobility and Security のトラブルシューティング
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Basic Mobility and Security の問題を追跡するには、次の手順を実行します。
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876854"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Basic Mobility and Security のトラブルシューティング

デバイスを Basic Mobility and Security に登録しようとするときに問題が発生している場合は、次の手順を実行して問題を追跡してください。 一般的な手順で問題が解決しない場合は、デバイスの種類に固有の手順を示す、後のセクションのいずれかを参照してください。

## <a name="steps-to-try-first"></a>最初に試す手順

開始するには、以下を確認します。

- デバイスが Intune などの別のモバイル デバイス管理プロバイダーに登録されていないか確認します。

- デバイスが正しい日付と時刻に設定されていることを確認します。

- デバイス上の別の WIFI または携帯ネットワークに切り替えます。

- Android または iOS デバイスの場合は、Intune ポータル サイト アプリをアンインストールし、デバイスに再インストールします。 

## <a name="ios-phone-or-tablet"></a>iOS スマートフォンまたはタブレット

- 必ず APNs 証明書を設定してください。 詳しくは [、「iOS デバイス用の APNs 証明書の作成」をご覧ください](create-an-apns-certificate-for-ios-devices.md)。

- [ **設定]** の [全般プロファイル] (または [デバイス管理]) で、管理プロファイルがインストール   >  ****   >  **** されていないか確認します。 削除されている場合は、削除します。

- "デバイスの登録に失敗しました" というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、デバイスにサインインしているユーザーに Exchange Online を含むライセンスが割り当てられている必要があります。

- "Profile failed to install" というエラー メッセージが表示された場合は、次のいずれかを試してください。

    - Safari がデバイスの既定のブラウザーであり、Cookie が無効になされていないか確認します。

    - デバイスを再起動し、デバイスに移動portal.manage.microsoft.com。 Microsoft 365 ユーザー ID とパスワードでサインインし、プロファイルを手動でインストールします。

## <a name="windows-rt"></a>Windows RT

- ドメインが Microsoft 365 に設定され、Basic Mobility and Security と一緒に動作する必要があります。 詳細については [、「Basic Mobility and Security のセットアップ」を参照してください](set-up.md)。
    
- [参加] を選択するのではなく、ユーザーが [ **オン]** を   選択している必要 **があります**。

## <a name="windows-10-pc"></a>Windows 10 PC

- ドメインが Microsoft 365 に設定され、Basic Mobility and Security と一緒に動作する必要があります。 詳細については [、「Basic Mobility and Security のセットアップ」を参照してください](set-up.md)。
    
- Azure Active Directory Premium がない場合は、[接続] を選択 **** するのではなく、ユーザーが [デバイス管理への登録] のみを選択   するように **します**。

## <a name="android-phone-or-tablet"></a>Android スマートフォンまたはタブレット

- デバイスが Android 4.4 以降を実行している必要があります。

- Chrome が最新であり、既定のブラウザーとして設定されている必要があります。

- "このデバイスを登録できなかった" というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、デバイスにサインインしているユーザーに Exchange Online を含むライセンスが割り当てられている必要があります。

- デバイスの通知領域を確認して、必要なエンド ユーザーの操作が保留中の場合は、操作を完了します。
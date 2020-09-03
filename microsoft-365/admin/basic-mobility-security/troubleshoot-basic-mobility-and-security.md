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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 基本的なモビリティとセキュリティの問題を追跡するには、次の手順を実行してください。
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336974"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>基本的なモビリティとセキュリティのトラブルシューティング

基本的なモビリティとセキュリティでデバイスを登録しようとしたときに問題が発生している場合は、次の手順を実行して問題を追跡します。 一般的な手順で問題が解決しない場合は、デバイスの種類に固有の手順が記載された後のセクションのいずれかを参照してください。

## <a name="steps-to-try-first"></a>最初に試す手順

開始するには、次の点を確認してください。

- デバイスが他のモバイルデバイス管理プロバイダー (Intune など) に登録されていないことを確認してください。
    
- デバイスが正しい日付と時刻に設定されていることを確認します。
    
- デバイス上の別の WIFI または携帯ネットワークに切り替えます。
    
- Android または iOS デバイスの場合は、デバイス上の Intune ポータルサイトアプリをアンインストールしてから再インストールします。 

## <a name="ios-phone-or-tablet"></a>iOS 電話またはタブレット

- APNs 証明書を設定していることを確認してください。 詳細については、「 [iOS のデバイス用の APNs 証明書を作成する](create-an-apns-certificate-for-ios-devices.md)」を参照してください。
    
- [ **Settings**   >  **General**   >  **profile (または Device Management)**] で、管理プロファイルがまだインストールされていないことを確認します。 その場合は、削除します。
    
- "デバイスの登録に失敗しました" というエラーメッセージが表示される場合は、Microsoft 365 にサインインして、デバイスにサインインしているユーザーに Exchange Online を含むライセンスが割り当てられていることを確認してください。
    
- "プロファイルをインストールできませんでした" というエラーメッセージが表示される場合は、次のいずれかを試してください。
    
    - Safari がデバイスの既定のブラウザーであること、および cookie が無効になっていないことを確認してください。
    
    - デバイスを再起動して、portal.manage.microsoft.com に移動します。 Microsoft 365 のユーザー ID とパスワードを使用してサインインし、プロファイルを手動でインストールしてみます。    

## <a name="windows-rt"></a>Windows RT

- 基本的なモビリティとセキュリティを使用するために、ドメインが Microsoft 365 で設定されていることを確認します。 詳細については、「 [基本モビリティとセキュリティを設定](set-up-basic-mobility-and-security.md)する」を参照してください。
    
- [参加] を選択せずに、ユーザーが **[オン**] を選択していることを確認し   ます。 **Join**    

## <a name="windows-10-pc"></a>Windows 10 PC

- 基本的なモビリティとセキュリティを使用するために、ドメインが Microsoft 365 で設定されていることを確認します。 詳細については、「 [基本モビリティとセキュリティを設定](set-up-basic-mobility-and-security.md)する」を参照してください。
    
- Azure Active Directory Premium を使用していない場合は、[接続] を選択するのではなく、ユーザーが [ **デバイス管理にのみ登録**] を選択していることを確認してください   。 **Connect**

## <a name="android-phone-or-tablet"></a>Android フォンまたはタブレット

- デバイスが Android 4.4 以降を実行していることを確認してください。
    
- Chrome が最新のものであり、既定のブラウザーとして設定されていることを確認します。
    
- "このデバイスを登録できませんでした" というエラーメッセージが表示された場合は、Microsoft 365 にサインインして、Exchange Online を含むライセンスが、デバイスにサインインしているユーザーに割り当てられていることを確認してください。
    
- デバイスの通知領域を調べて、必要なエンドユーザー操作が保留中であるかどうかを確認し、完了している場合は、操作を完了します。
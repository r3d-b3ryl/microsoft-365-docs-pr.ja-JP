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
description: 基本的なモビリティとセキュリティの問題を追跡するには、次の手順を試してください
ms.openlocfilehash: 1b1b7d67eb07c67c320554c1d64701983da30e15
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65636066"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>基本的なモビリティとセキュリティのトラブルシューティング

Basic Mobility and Security にデバイスを登録しようとしたときに問題が発生している場合は、こちらの手順を試して問題を追跡してください。 一般的な手順で問題が解決しない場合は、後のセクションの 1 つで、デバイスの種類に固有の手順を参照してください。

## <a name="steps-to-try-first"></a>最初に試す手順

開始するには、次の項目を確認します。

- デバイスが別のモバイル デバイス管理プロバイダー (Intuneなど) にまだ登録されていないことを確認します。

- デバイスが正しい日付と時刻に設定されていることを確認します。

- デバイス上の別の WIFI または携帯ネットワークに切り替えます。

- AndroidデバイスまたはiOS デバイスの場合は、Intune ポータル サイト アプリをアンインストールしてデバイスに再インストールします。 

## <a name="ios-phone-or-tablet"></a>電話またはTablet PCをiOSする

- APNs 証明書が設定されていることを確認します。 詳細については、「[iOS デバイス用の APNs 証明書を作成する」を参照してください](create-an-apns-certificate-for-ios-devices.md)。

- **設定** > **GeneralProfile** >  **(またはデバイス管理)** で、管理プロファイルがまだインストールされていないことを確認します。 ある場合は、削除します。

- "デバイスの登録に失敗しました" というエラー メッセージが表示された場合は、Microsoft 365にサインインし、Exchange Onlineを含むライセンスがデバイスにサインインしているユーザーに割り当てられていることを確認します。

- "プロファイルのインストールに失敗しました" というエラー メッセージが表示された場合は、次のいずれかを試してください。

    - Safari がデバイスの既定のブラウザーであり、Cookie が無効になっていないことを確認します。

    - デバイスを再起動し、portal.manage.microsoft.com に移動します。 Microsoft 365ユーザー ID とパスワードでサインインし、プロファイルを手動でインストールします。

## <a name="windows-rt"></a>Windows RT

- Basic Mobility and Security を使用するようにドメインがMicrosoft 365に設定されていることを確認します。 詳細については、「 [基本的なモビリティとセキュリティの設定](set-up.md)」を参照してください。
    
- ユーザーが **[結合**] ではなく [**有効にする**] を選択していることを確認します。

## <a name="windows-10-pc"></a>WINDOWS 10 PC

- Basic Mobility and Security を使用するようにドメインがMicrosoft 365に設定されていることを確認します。 詳細については、「 [基本的なモビリティとセキュリティの設定](set-up.md)」を参照してください。
    
- Azure Active Directory Premiumがない限り、ユーザーが [Connectを選択するのではなく **、デバイス管理に登録** する] を選択していることを確認 **します。**

## <a name="android-phone-or-tablet"></a>電話またはTablet PCをAndroidする

- デバイスがAndroid実行されていることを確認します。

- Chrome が最新の状態で、既定のブラウザーとして設定されていることを確認します。

- "このデバイスを登録できませんでした" というエラー メッセージが表示された場合は、Microsoft 365にサインインし、Exchange Onlineを含むライセンスがデバイスにサインインしているユーザーに割り当てられていることを確認します。

- デバイスの通知領域を確認して、必要なエンド ユーザーアクションが保留中であるかどうかを確認し、そのアクションが完了しているかどうかを確認します。
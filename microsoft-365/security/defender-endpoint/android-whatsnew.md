---
title: Android のエンドポイント向け Microsoft Defender の新機能
description: Android 上のエンドポイント向け Microsoft Defender の以前のバージョンの主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 820c93804615e9aafcb34052d65f09bbd3e3d1c9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717518"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android のエンドポイント向け Microsoft Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later"></a>Android 11 以降を実行しているエンドポイント用 Microsoft Defender の今後のアクセス許可の変更

11 月には、Microsoft Defender for Endpoint が [Android](https://developer.android.com/distribute/play-policies#APILevel30) API 30 に移行する必要があります。 この移動では、Android 11 以降 [を](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) 実行しているデバイスの新しい記憶域のアクセス許可を求めるメッセージが表示されます。 ユーザーは、11 月バージョンの Microsoft Defender for Endpoint に更新した後、この新しい記憶域のアクセス許可を受け入れる必要があります。 これにより、デバイス上で Defender の 「アプリ セキュリティ」 機能が引き続き使用されます。 詳細については、以下のセクションの詳細を参照してください。

**これは組織にどのような影響を与えるのか。**

これらの変更は、Android 11 以降を実行し、11 月のアプリに更新されたデバイスで Microsoft Defender for Endpoint を使用している場合にのみ影響します。 この設定は、この設定を使用Microsoft エンドポイント マネージャー。前述の Google API の変更により、ユーザーはアクションを実行する必要があります。

- **ユーザー エクスペリエンス:** ユーザーは、アプリのセキュリティに対するアクセス許可が見つからないことを示す通知を受け取ります。 ユーザーがこのアクセス許可を拒否すると、デバイスで 'App security' 機能が無効になります。 ユーザーがアクセス許可を承諾または拒否しない場合は、デバイスのロックを解除するか、承認されるまでアプリを開く際に、引き続きプロンプトが表示されます。

>[!NOTE] 
> 組織が 'タンパープロテクション' 機能をプレビューしている場合、最新バージョンへの更新から 7 日以内に新しい記憶域のアクセス許可がユーザーによって付与されていない場合、ユーザーは企業リソースへのアクセスを失う可能性があります。

**準備に必要な事柄:**

Microsoft Defender for Endpoint アプリの 11 月バージョンに更新した後に、ユーザーが新しいアクセス許可を受け入れる必要がある場合は、ユーザーとヘルプデスクに通知します (該当する場合)。 アクセス許可を受け入れるには、次の必要があります。

1. Defender アプリ内通知をタップするか、Microsoft Defender for Endpoint アプリを開きます。 ユーザーには、必要なアクセス許可を一覧表示する画面が表示されます。 アクセス許可の横に緑色のチェック マークStorage表示されます。

2. [開始 **] をタップします**。

3. [アクセスを許可してすべての **ファイルを管理する] のトグルをタップします。** 

  >[!NOTE] 
  >このアクセス許可により、Microsoft Defender for Endpoint はユーザーのデバイス上のストレージにアクセスできます。これにより、悪意のあるアプリや不要なアプリを検出して削除できます。 Microsoft Defender for Endpoint は、Android アプリ パッケージ ファイル (.apk) にのみアクセス/スキャンし、ワーク プロファイルを持つデバイスでは、作業関連ファイルのみをスキャンします。

4. これで、デバイスは保護されています。






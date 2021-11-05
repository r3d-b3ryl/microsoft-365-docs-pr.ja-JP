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
ms.openlocfilehash: c29570668f6fcf542ef3336c8053b395331fcce2
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792546"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android のエンドポイント向け Microsoft Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Android 11 以降を実行しているエンドポイント用 Microsoft Defender の今後のアクセス許可の変更 (2021 年 11 月)
リリース ビルド: 1.0.3501.0301 リリース月: 2021 年 11 月

Microsoft Defender for Endpoint は [、Google](https://developer.android.com/distribute/play-policies#APILevel30) によって Android API 30 へのアップグレードを義務付けされています。 この変更により、Android 11 以降 [を](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) 実行しているデバイスに対する新しい記憶域のアクセス許可を求めるメッセージが表示されます。 ユーザーは、リリース ビルド 1.0.3501.0301 以降で Defender アプリを更新した後、この新しいストレージアクセス許可を受け入れる必要があります。 これにより、Defender の 「アプリセキュリティ」 機能が中断することなく機能します。 詳細については、以下のセクションの詳細を参照してください。

**これは組織にどのような影響を与えるのか。**

これらの変更は、Android 11 以降を実行しているデバイスで Microsoft Defender for Endpoint を使用し、Defender を更新してビルド 1.0.3501.0301 以降をリリースする場合に影響します。 この設定は、管理者が管理者によって構成Microsoft エンドポイント マネージャー。上記の Google API の変更により、ユーザーはアクションを実行する必要があります。

- **ユーザー エクスペリエンス:** ユーザーは、アプリのセキュリティに対するアクセス許可が見つからないことを示す通知を受け取ります。 ユーザーがこのアクセス許可を拒否すると、デバイスで 'App security' 機能が無効になります。 ユーザーがアクセス許可を受け入れるか拒否しない場合、承認されるまで、デバイスのロックを解除するかアプリを開く際に、引き続きプロンプトが表示されます。

>[!NOTE] 
> 組織が 'タンパープロテクション' 機能をプレビューしている場合、最新バージョンへの更新から 7 日以内に新しい記憶域のアクセス許可がユーザーによって付与されていない場合、ユーザーは企業リソースへのアクセスを失う可能性があります。

**準備に必要な事柄:**

Defender を更新して 1.0.3501.0301 以降のバージョンをビルドした後に、ユーザーが新しいアクセス許可を受け入れる必要がある場合は、ユーザーとヘルプデスクに通知します (該当する場合)。 アクセス許可を受け入れるには、次の必要があります。

1. Defender アプリ内通知をタップするか、Microsoft Defender for Endpoint アプリを開きます。 ユーザーには、必要なアクセス許可を一覧表示する画面が表示されます。 アクセス許可の横に緑色のチェック マークStorage表示されます。

2. [開始 **] をタップします**。

3. [アクセスを許可してすべての **ファイルを管理する] のトグルをタップします。** 

4. これで、デバイスは保護されています。

  >[!NOTE] 
  >このアクセス許可により、Microsoft Defender for Endpoint はユーザーのデバイス上のストレージにアクセスできます。これにより、悪意のあるアプリや不要なアプリを検出して削除できます。 Microsoft Defender for Endpoint accesses/scans Android app package file (.apk) のみ。 仕事用プロファイルを持つデバイスでは、Denender は作業関連のファイルのみをスキャンします。








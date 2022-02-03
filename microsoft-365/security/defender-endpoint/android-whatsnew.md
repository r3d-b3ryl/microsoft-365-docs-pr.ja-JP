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
ms.openlocfilehash: 1fca5a6762642968310b7165db09d827c06c0cbd
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321869"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android のエンドポイント向け Microsoft Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="threat-and-vulnerability-management"></a>脅威と脆弱性の管理

2022 年 1 月 25 日、Android と iOS の脅威と脆弱性の管理の一般提供を発表しました。 詳細については、 [techcommunity の投稿を参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)。

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Android 11 以降を実行しているエンドポイント用 Microsoft Defender の今後のアクセス許可の変更 (2021 年 11 月)

リリース ビルド: 1.0.3501.0301 リリース月: 2021 年 11 月 Microsoft Defender for Endpoint は [、Google が Android](https://developer.android.com/distribute/play-policies#APILevel30) API 30 にアップグレードするために必要なこの更新プログラムをリリースしました。 この変更により、Android 11 以降を[](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)実行しているデバイスに対して、新しいストレージアクセス許可へのアクセスを求めるユーザーにメッセージが表示されます。 ユーザーは、リリース ビルド 1.0.3501.0301 以降で Defender アプリを更新した後、この新しいストレージアクセス許可を受け入れる必要があります。 これにより、Defender for Endpoint のアプリセキュリティ機能が中断することなく確実に機能します。 詳細については、次のセクションを参照してください。

**これは組織にどのような影響を与えるのか。** これらの変更は、Android 11 以降を実行しているデバイスで Microsoft Defender for Endpoint を使用し、Defender for Endpoint を更新してビルド 1.0.3501.0301 以降をリリースする場合に影響します。

> [!NOTE]
> 新しい記憶域のアクセス許可は、管理者が [自動承認] を [自動承認] に構成Microsoft エンドポイント マネージャー。 ユーザーは、このアクセス許可へのアクセスを提供するためにアクションを実行する必要があります。

- **ユーザー エクスペリエンス:** ユーザーは、アプリのセキュリティに対するアクセス許可が見つからないことを示す通知を受け取ります。 ユーザーがこのアクセス許可を拒否すると、デバイスで 'App security' 機能が無効になります。 ユーザーがアクセス許可を受け入れるか拒否しない場合、承認されるまで、デバイスのロックを解除するかアプリを開く際に、引き続きプロンプトが表示されます。

> [!NOTE]
> 組織が 'タンパープロテクション' 機能をプレビューしている場合、最新バージョンへの更新から 7 日以内に新しい記憶域のアクセス許可がユーザーによって付与されていない場合、ユーザーは企業リソースへのアクセスを失う可能性があります。

**準備に必要な事柄:**

Defender for Endpoint を更新して 1.0.3501.0301 以降のバージョンをビルドした後で、ユーザーが新しいアクセス許可を受け入れる必要がある場合は、ユーザーとヘルプデスクに通知します (該当する場合)。 アクセス許可を受け入れるには、次の必要があります。

1. Defender for Endpoint アプリ内通知をタップするか、Defender for Endpoint アプリを開きます。 ユーザーには、必要なアクセス許可を一覧表示する画面が表示されます。 アクセス許可の横に緑色のチェック マークStorage表示されます。

2. [開始 **] をタップします**。

3. [アクセスを許可してすべての **ファイルを管理する] のトグルをタップします。**

4. これで、デバイスは保護されています。

  > [!NOTE]
  > このアクセス許可により、Microsoft Defender for Endpoint はユーザーのデバイス上のストレージにアクセスできます。これにより、悪意のあるアプリや不要なアプリを検出して削除できます。 Microsoft Defender for Endpoint accesses/scans Android app package file (.apk) のみ。 作業プロファイルを持つデバイスでは、Defender for Endpoint は作業関連のファイルのみをスキャンします。

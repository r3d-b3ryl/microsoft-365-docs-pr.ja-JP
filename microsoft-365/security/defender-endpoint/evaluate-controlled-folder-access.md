---
title: 制御されたフォルダー アクセスを評価する
description: フォルダー アクセスの制御によって、悪意のあるアプリによってファイルが変更されるのを保護する方法について説明します。
keywords: エクスプロイト保護、Windows 10、Windows Defender、ランサムウェア、保護、評価、テスト、デモ、試す
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 708d7d271e03b127460d5b2aa2745568d920a198
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042880"
---
# <a name="evaluate-controlled-folder-access"></a>制御されたフォルダー アクセスを評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)


[フォルダー アクセスの制御は](controlled-folders.md) 、疑わしいアプリや悪意のあるアプリによる変更からドキュメントやファイルを保護する機能です。 フォルダー アクセスの制御は、サーバー 2019、Windows Server 2022、WindowsクライアントでWindows 10されます。

特に、ファイルを暗号化して人質[](https://www.microsoft.com/wdsi/threats/ransomware)に保持しようとするランサムウェアから保護する場合に役立ちます。

この記事では、フォルダー アクセスの制御を評価するのに役立ちます。 監査モードを有効にして、組織で機能を直接テストする方法について説明します。

> [!TIP]
> また、Microsoft Defender for Endpoint のデモ シナリオ web サイト demo.wd.microsoft.com 機能 [が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認することもできます。

## <a name="use-audit-mode-to-measure-impact"></a>監査モードを使用して影響を測定する

監査モードで管理フォルダー アクセスを有効にして、完全に有効にした場合に何が起こったかのレコードを確認します。 組織で機能がどのように機能されるかをテストして、その機能が業務上のアプリに影響を与えなかねない方法を確認します。 また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。

監査モードを有効にするには、次の PowerShell コマンドレットを使用します。

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> 組織でフォルダー アクセスの制御方法を完全に監査する場合は、管理ツールを使用して、ネットワーク内のデバイスにこの設定を展開する必要があります。
また、グループ ポリシー、Intune、モバイル デバイス管理 (MDM)、または Microsoft エンドポイント マネージャー を使用して、メインの管理フォルダー アクセス トピックで説明したように、設定を構成および[展開することもできます](controlled-folders.md)。

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>イベント ビューアーで管理されたフォルダー アクセス イベントWindows確認する

次の制御されたフォルダー アクセス イベントは、Microsoft/Windows Windows/Windows Defender/操作フォルダーの下のイベント ビューアーに表示されます。

イベント ID | 説明
-|-
 5007 | 設定が変更された場合のイベント
 1124 | 監査されたフォルダー アクセス イベント
 1123 | ブロックされたフォルダー アクセス イベント

> [!TIP]
> ログを一Windows[するイベント転送](/windows/win32/wec/setting-up-a-source-initiated-subscription)サブスクリプションを構成できます。 

## <a name="customize-protected-folders-and-apps"></a>保護されたフォルダーとアプリをカスタマイズする

評価中に、保護されたフォルダーの一覧に追加したり、特定のアプリでファイルを変更したりすることもできます。

グループ [ポリシー](controlled-folders.md) 、PowerShell、MDM 構成サービス プロバイダー (CSP) などの管理ツールを使用して機能を構成するには、「フォルダー アクセスを制御した重要なフォルダーを保護する」を参照してください。

## <a name="see-also"></a>関連項目

* [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
* [Microsoft Defender for Endpoint の評価](evaluate-mde.md)
* [監査モードを使用する](audit-windows-defender.md)

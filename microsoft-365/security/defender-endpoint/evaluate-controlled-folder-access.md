---
title: 制御されたフォルダー アクセスを評価する
description: フォルダー アクセスの制御が、悪意のあるアプリによってファイルが変更されないように保護する方法について説明します。
keywords: エクスプロイト保護, Windows 10, Windows 11, Windows Defender, ランサムウェア, 保護, 評価, テスト, デモ, 試す
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: 8e251222d71ad9559084ec39d7fa65a18b9e2c1a
ms.sourcegitcommit: c314e989202dc1c9c260fffd459d53bc1f08514e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66717164"
---
# <a name="evaluate-controlled-folder-access"></a>制御されたフォルダー アクセスを評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)


[フォルダー アクセスの制御](controlled-folders.md) は、疑わしいアプリや悪意のあるアプリによる変更からドキュメントやファイルを保護するのに役立つ機能です。 フォルダー アクセスの制御は、Windows Server 2019、Windows Server 2022、Windows 10、およびWindows 11 クライアントでサポートされています。

特に、ファイルを暗号化して人質にしようとする [ランサムウェア](https://www.microsoft.com/wdsi/threats/ransomware) から保護するのに役立ちます。

この記事は、フォルダー アクセスの制御を評価するのに役立ちます。 組織で機能を直接テストできるように、監査モードを有効にする方法について説明します。

## <a name="use-audit-mode-to-measure-impact"></a>監査モードを使用して影響を測定する

監査モードで制御されたフォルダー アクセスを有効にして、完全に有効にした場合に発生した内容のレコードを確認します。 この機能が組織内でどのように機能するかをテストして、基幹業務アプリに影響を与えないことを確認します。 また、一定期間にわたって一般的に発生する疑わしいファイル変更試行の数を把握することもできます。

監査モードを有効にするには、次の PowerShell コマンドレットを使用します。

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> 組織内でフォルダー アクセスの制御方法を完全に監査する場合は、管理ツールを使用してこの設定をネットワーク内のデバイスに展開する必要があります。
また、グループ ポリシー、Intune、モバイル デバイス管理 (MDM)、または Microsoft エンドポイント マネージャーを使用して、メインの[フォルダー アクセス制御トピック](controlled-folders.md)で説明されているように、設定を構成および展開することもできます。

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Windows イベント ビューアーで制御されたフォルダー アクセス イベントを確認する

次のフォルダー アクセス制御イベントは、Windows イベント ビューアーの Microsoft/Windows/Windows Defender/Operational フォルダーの下に表示されます。

イベント ID | 説明
-|-
 5007 | 設定が変更された場合のイベント
 1124 | 監査されたフォルダー アクセスの制御イベント
 1123 | ブロックされたフォルダー アクセス イベント

> [!TIP]
> ログを一元的に収集するように [Windows イベント転送サブスクリプション](/windows/win32/wec/setting-up-a-source-initiated-subscription) を構成できます。 

## <a name="customize-protected-folders-and-apps"></a>保護されたフォルダーとアプリをカスタマイズする

評価中に、保護されたフォルダーの一覧に追加するか、特定のアプリにファイルの変更を許可することができます。

グループ ポリシー、PowerShell、MDM 構成サービス プロバイダー (CSP) を含む管理ツールを使用して機能を構成するには、「[フォルダー アクセスが制御された重要なフォルダーを保護](controlled-folders.md)する」を参照してください。

## <a name="see-also"></a>関連項目

* [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
* [Microsoft Defender for Endpoint の評価](evaluate-mde.md)
* [監査モードを使用する](audit-windows-defender.md)

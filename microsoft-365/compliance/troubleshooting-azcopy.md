---
title: 高度な電子情報開示での AzCopy のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery でエラー修復のために 365 以外のデータOffice読み込む場合の Azure AzCopy のエラーのトラブルシューティングを行います。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919293"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>高度な電子情報開示での AzCopy のトラブルシューティング

Advanced eDiscovery でエラー修復のために Microsoft 365 以外のデータまたはドキュメントを読み込む場合、ユーザー インターフェイスは、アップロードするファイルの保存場所とファイルのアップロード先の Azure ストレージの場所を含むパラメーターを含む Azure AzCopy コマンドを提供します。 ドキュメントをアップロードするには、このコマンドをコピーし、ローカル コンピューターのコマンド プロンプトで実行します。  次のスクリーンショットは、AzCopy コマンドの例を示しています。

![Microsoft 365 以外のファイルをアップロードする](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常、指定されたコマンドは、実行時に機能します。 ただし、表示されるコマンドが正常に実行されない場合があります。 考えられる理由を次に示します。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>サポートされているバージョンの AzCopy がローカル コンピューターにインストールされていない

現時点では、AzCopy v8.1 を使用して、高度な電子情報開示で Microsoft 365 以外のデータを読み込む必要があります。 前のスクリーンショットに示した [ファイルのアップロード] ページに表示される AzCopy コマンドは、AzCopy v8.1 を使用していない場合にエラーを返します。 このバージョンをインストールするには [、「Windows で AzCopy v8.1 を](/previous-versions/azure/storage/storage-use-azcopy)使用してデータを転送する」を参照してください。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy がローカル コンピューターにインストールされていないか、既定の場所にインストールされていない

AzCopy がインストールされていないか、既定のインストール場所 (つまり) 以外の場所にインストールされている場合は、AzCopy コマンドを実行すると、次のエラー メッセージが `%ProgramFiles(x86)%` 表示される場合があります。

> システムは、指定されたパスを見つけ出す必要があります。

AzCopy がローカル コンピューターにインストールされていない場合は、「Windows の [AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)を使用してデータを転送する」でインストール情報を確認できます。 既定の場所にインストールしてください。

AzCopy がインストールされているが、既定の場所とは異なる場所にインストールされている場合は、コマンドをコピーしてテキスト ファイルに貼り付け、パスを AzCopy がインストールされている場所に変更できます。 たとえば、Azcopy がにある場合は、コマンドの最初の部分をに `%ProgramFiles%` 変更 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` できます `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。 この変更を行った後、テキスト ファイルからコピーし、コマンド プロンプトを実行します。

> [!TIP]
> AzCopy が別の場所にインストールされている場合は、既定のインストール場所をアンインストールしてから、既定の場所に再インストールしてください。 これは、将来この問題を防ぐのに役立ちます。
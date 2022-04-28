---
title: 電子情報開示での AzCopy のトラブルシューティング (プレミアム)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 電子情報開示 (プレミアム) でエラー修復のためにOffice 365以外のデータを読み込む際の Azure AzCopy のエラーのトラブルシューティングを行います。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 85d51e7ecb59f8423f0a509725c6a1c1defd3adf
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092329"
---
# <a name="troubleshoot-azcopy-in-ediscovery-premium"></a>電子情報開示での AzCopy のトラブルシューティング (プレミアム)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview 電子情報開示 (プレミアム) でエラー修復のためにMicrosoft 365以外のデータまたはドキュメントを読み込む場合、ユーザー インターフェイスには、アップロードするファイルの保存場所とファイルのアップロード先となる Azure ストレージの場所を含むパラメーターを含む Azure AzCopy コマンドが用意されています。 ドキュメントをアップロードするには、このコマンドをコピーし、ローカル コンピューターのコマンド プロンプトで実行します。  次のスクリーンショットは、AzCopy コマンドの例を示しています。

![Microsoft 365以外のファイルをアップロードします。](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常、指定されたコマンドは、実行時に機能します。 ただし、表示されるコマンドが正常に実行されない場合があります。 考えられる理由をいくつか次に示します。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>サポートされているバージョンの AzCopy がローカル コンピューターにインストールされていない

現時点では、AzCopy v8.1 を使用して、電子情報開示 (プレミアム) にMicrosoft 365以外のデータを読み込む必要があります。 前のスクリーンショットに示した **[アップロード ファイル**] ページに表示される AzCopy コマンドは、AzCopy v8.1 を使用していない場合にエラーを返します。 このバージョンをインストールするには、[Windowsの AzCopy v8.1 を使用したデータの転送に関するページを参照](/previous-versions/azure/storage/storage-use-azcopy)してください。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy がローカル コンピューターにインストールされていないか、既定の場所にインストールされていません

AzCopy がインストールされていない場合、または既定のインストール場所 (つまり) 以外の場所にインストールされている場合は `%ProgramFiles(x86)%`、AzCopy コマンドを実行すると、次のエラーが発生する可能性があります。

> 指定されたパスがシステムで見つかりません。

AzCopy がローカル コンピューターにインストールされていない場合は、Windowsの [AzCopy v8.1 を使用したデータの転送に関](/previous-versions/azure/storage/storage-use-azcopy)するページでインストール情報を確認できます。 必ず既定の場所にインストールしてください。

AzCopy がインストールされているが、既定の場所とは異なる場所にインストールされている場合は、コマンドをコピーし、テキスト ファイルに貼り付けてから、AzCopy がインストールされている場所にパスを変更できます。 たとえば、Azcopy が配置`%ProgramFiles%`されている場合は、コマンド`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe``%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`の最初の部分を . この変更を行った後、テキスト ファイルからコピーし、コマンド プロンプトを実行します。

> [!TIP]
> AzCopy が別の場所にインストールされている場合は、既定のインストール場所をアンインストールしてから、既定の場所に再インストールすることを検討してください。 これは、将来的にこの問題を防ぐのに役立ちます。
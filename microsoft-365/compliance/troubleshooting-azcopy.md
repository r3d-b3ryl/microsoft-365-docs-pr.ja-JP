---
title: Advanced eDiscovery での AzCopy のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Office 以外の365データを読み込み中に、高度な電子情報開示でエラーを修復するために、Azure AzCopy のエラーをトラブルシューティングします。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: caec3011c89e027f1b78991a3dad842ff4b8c8aa
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434280"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Advanced eDiscovery での AzCopy のトラブルシューティング

Advanced eDiscovery でエラーを修復するために Microsoft 以外の365データまたはドキュメントを読み込む場合、ユーザーインターフェイスは、アップロードするファイルが保存されている場所と、ファイルがアップロードされる Azure ストレージの場所を含む、Azure AzCopy コマンドを提供します。 ドキュメントをアップロードするには、このコマンドをコピーして、ローカルコンピューターのコマンドプロンプトで実行します。  次のスクリーンショットは、AzCopy コマンドの例を示しています。

![Microsoft 以外の365ファイルのアップロード](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常、提供されるコマンドは、実行時に機能します。 ただし、表示されるコマンドが正常に実行されない場合もあります。 考えられるいくつかの理由を次に示します。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>サポートされているバージョンの AzCopy がローカルコンピューターにインストールされていません

現時点では、Microsoft 以外の365データを Advanced eDiscovery で読み込むには、AzCopy v1.1 を使用する必要があります。 AzCopy v2.0 を使用していない場合、前のスクリーンショットに表示されている [**ファイルのアップロード**] ページに表示される azcopy コマンドはエラーを返します。 このバージョンをインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 でデータを転送する」を参照してください。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy がローカルコンピューターにインストールされていないか、既定の場所にインストールされていません

AzCopy がインストールされていない場合や、既定のインストール先 (つまり) 以外の場所にインストールされている場合 `%ProgramFiles(x86)%` 、azcopy コマンドを実行すると、次のエラーが表示されることがあります。

> システムで指定されたパスが見つかりません。

AzCopy がローカルコンピューターにインストールされていない場合は、「 [Windows の AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 でデータを転送する」のインストール情報を参照できます。 必ず既定の場所にインストールしてください。

AzCopy がインストールされていても、既定の場所とは異なる場所にインストールされている場合は、コマンドをコピーしてテキストファイルに貼り付け、次に、AzCopy がインストールされている場所へのパスを変更することができます。 たとえば、Azcopy がにある場合は、 `%ProgramFiles%` コマンドの最初の部分をからに変更でき `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` ます。 この変更を行った後、テキストファイルからコピーし、コマンドプロンプトで実行します。

> [!TIP]
> AzCopy が既定のインストール先以外の場所にインストールされている場合は、それをアンインストールしてから、既定の場所に再インストールすることを検討してください。 これにより、今後この問題を回避することができます。

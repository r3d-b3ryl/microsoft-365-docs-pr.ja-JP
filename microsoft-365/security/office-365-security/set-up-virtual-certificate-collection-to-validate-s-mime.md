---
title: 仮想証明書のコレクションをセットアップする - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理者は、Exchange Online で S/MIME 証明書の検証に使用される仮想証明書コレクションを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4537ecfa6d800294af9572e462ce18491ce2c441
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290479"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>S/MIME を検証するために Exchange Online で仮想証明書のコレクションをセットアップする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


管理者は、S/MIME 証明書の検証に使用される Exchange Online の仮想証明書コレクションを構成する必要があります。 この仮想証明書コレクションは、SST ファイル名拡張子を持つ証明書ストアとして設定されます。 SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれます。

## <a name="create-and-save-an-sst"></a>SST を作成して保存する

この SST 証明書ストア ファイルを作成するには、Windows PowerShell の **Export-Certificate** コマンドレットを使用して信頼されたコンピューターから証明書をエクスポートし _、Type_ 値を SST として指定します。 手順については [、「Export-Certificate」を参照してください](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。

SST 証明書ストア ファイルを取得したら、Exchange Online PowerShell で次の構文を使用して、SST ファイルの内容を Exchange Online 仮想証明書ストアに保存します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

この例では、SST ファイル C:\My Documents\Exported Certificate Store.sst をインポートします。

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

構文およびパラメーターの詳細については [、「Set-SmimeConfig」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。

## <a name="ensuring-a-certificate-is-valid"></a>証明書が有効なことを確認する

Exchange Online では、証明書の検証に SST だけが使用されます。

## <a name="more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)

---
title: Microsoft 365のディレクトリ同期を無効にする
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: この記事では、PowerShell を使用してMicrosoft 365のディレクトリ同期を無効にする方法について説明します。
ms.openlocfilehash: 5082f89032c17e549f11f8397126f6d059937c48
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077342"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Microsoft 365のディレクトリ同期を無効にする
PowerShell を使用してディレクトリ同期を無効にし、同期されたユーザーをクラウド専用に変換できます。 ただし、トラブルシューティング手順としてディレクトリ同期を無効にすることはお勧めしません。 ディレクトリ同期のトラブルシューティングに関するサポートが必要な場合は、「[Microsoft 365ディレクトリ同期に関する問題の修正」を](fix-problems-with-directory-synchronization.md)参照してください。 
  
必要に応じて、ビジネス製品の[サポートにお問い合わせください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。
  
## <a name="turn-off-directory-synchronization"></a>ディレクトリ同期を無効にする  
ディレクトリ同期を無効にするには:
  
1. まず、必要なソフトウェアをインストールし、Microsoft 365 サブスクリプションに接続します。 手順については、[Windows PowerShellのMicrosoft Azure Active Directory モジュールに関するConnectを](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)参照してください。
    
2. [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) を使用して、ディレクトリ同期を無効にします。 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>このコマンドを使用する場合は、ディレクトリ同期を再度有効にするには、72 時間待つ必要があります。
>

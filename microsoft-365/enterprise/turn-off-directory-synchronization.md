---
title: ユーザーのディレクトリ同期をオフMicrosoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: この記事では、PowerShell を使用してユーザーのディレクトリ同期をオフにする方法Microsoft 365。
ms.openlocfilehash: 6f22f4ad493dfc5a78d98dc057bcef0d500d7405f2e43ca9a493c74c7d8605eb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53878109"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>ユーザーのディレクトリ同期をオフMicrosoft 365
PowerShell を使用すると、ディレクトリ同期をオフにし、同期されたユーザーをクラウド専用に変換できます。 ただし、トラブルシューティング手順としてディレクトリ同期をオフにすることをお勧めしません。 ディレクトリ同期のトラブルシューティングに関するサポートが必要な場合は、「ディレクトリ同期に関する問題を修正する」の記事[Microsoft 365](fix-problems-with-directory-synchronization.md)してください。 
  
[必要に応じて](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 、ビジネス製品のサポートにお問い合わせください。
  
## <a name="turn-off-directory-synchronization"></a>ディレクトリ同期を無効にする  
ディレクトリ同期をオフにする方法:
  
1. まず、必要なソフトウェアをインストールし、サブスクリプションにMicrosoft 365します。 手順については、「Connect[モジュールのMicrosoft Azure Active Directory」を参照Windows PowerShell。](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
2. [Set-MsolDirSyncEnabled を使用してディレクトリ](/previous-versions/azure/dn194097(v=azure.100))同期を無効にします。 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>このコマンドを使用する場合は、ディレクトリ同期を有効に戻す前に 72 時間待機する必要があります。
>

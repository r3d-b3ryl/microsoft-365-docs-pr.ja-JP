---
title: SharePoint Online のウイルス検出
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639827"
---
# <a name="virus-detection-in-sharepoint-online"></a>SharePoint Online のウイルス検出

> [!IMPORTANT]
> この機能を使用するには、Office 365 Advanced Threat Protection (ATP) が必要です。 詳細については、「[SharePoint、OneDrive、Microsoft の Office 365 ATP を有効にする](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams)」を参照してください。

Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
  
> [!IMPORTANT]
> SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。 戦略とベストプラクティスの詳細については、「[セキュリティロードマップ](security-roadmap.md)」を参照してください。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Office 365 では一般的なウイルス検出エンジンが使用されます。 エンジンは SharePoint Online 内で非同期に実行され、アップロード後にファイルをスキャンします。 ファイルでウイルスが見つかると、フラグが設定されて、そのファイルはダウンロードできなくなります。 2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。
  
動作は次のとおりです。
  
1. ユーザーがファイルを SharePoint Online にアップロードします。
    
2. ウイルス検出エンジンによってファイルがスキャンされます。
    
3. ウイルスが見つかると、ウイルス エンジンによって、感染していることを示すプロパティがファイルに設定されます。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

SharePoint Online からファイルをダウンロードすることはできません。
  
動作は次のとおりです。
  
1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
    
2. ウイルスが検出されたという警告がユーザーに提示されます。 ユーザーには、ファイルをダウンロードして、独自のウイルスソフトウェアを使用して駆除を試行するオプションが与えられます。

> [!NOTE]
> Set-spotenant コマンドレットを**DisallowInfectedFileDownload**パラメーターと共に使用して、ウイルス対策の警告ウィンドウであっても、検出されたファイルをダウンロードできないようにすることができます。 「[DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。
  


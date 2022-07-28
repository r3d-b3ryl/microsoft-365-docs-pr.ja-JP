---
title: SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス保護
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: SharePoint Online が、ユーザーがアップロードしたファイル内のウイルスを検出し、ユーザーがファイルをダウンロードまたは同期できないようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b04e9a1ca2e722a2f581441f44716c22be7a1635
ms.sourcegitcommit: 1e53bf8208c30d7b60685896207cc1142bebf34a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67059691"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス保護

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

Microsoft 365 では、ユーザーが SharePoint Online、OneDrive、および Microsoft Teams にアップロードするファイルをスキャンするために、一般的なウイルス検出エンジンを使用します。 この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれます。

> [!IMPORTANT]
> 組み込みのウイルス対策機能は、ウイルスを含むのに役立つ方法です。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対し、さまざまなレイヤーでマルウェア対策の保護を調査して実装し、エンタープライズ インフラストラクチャをセキュリティで保護するためのベスト プラクティスを適用することをお勧めします。 戦略とベスト プラクティスの詳細については、「 [セキュリティ ロードマップ](security-roadmap.md)」を参照してください。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされた場合はどうなりますか?

Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に (ファイルのアップロードから独立して) 実行されます。 **すべてのファイルは自動的にスキャンされません**。 ヒューリスティックによって、スキャンするファイルが決定されます。 ファイルにウイルスが含まれていることが検出されると、ファイルにフラグが設定されます。 2018 年 4 月に、スキャンされたファイルの 25 MB の制限を削除しました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。
2. SharePoint Online は、ウイルス スキャン プロセスの一環として、後でファイルがスキャンの条件を満たしているかどうかを判断します。
3. ファイルがスキャンの条件を満たしている場合は、ウイルス検出エンジンによってファイルがスキャンされます。
4. スキャンされたファイル内でウイルスが見つかった場合、ウイルス エンジンは、ファイルが感染していることを示すプロパティをファイルに設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

既定では、ユーザーは SharePoint Online から感染したファイルをダウンロードできます。 動作は次のとおりです。

1. Web ブラウザーでは、ユーザーが SharePoint Online からファイルのダウンロードを試みます。このファイルは、感染している可能性があります。
2. ファイル内でウイルスが検出されたことを示す警告がユーザーに表示されます。 ユーザーには、ダウンロードを続行し、デバイス上のウイルス対策ソフトウェアを使用してクリーンアップを試みるオプションが与えられます。

この動作を変更して、ユーザーが感染したファイルをダウンロードできないようにするには、ウイルス対策の警告ウィンドウからでも、管理者は SharePoint Online PowerShell の **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用できます。 *DisallowInfectedFileDownload* パラメーターに$true値を指定すると、ユーザーの検出されたファイルやボックされたファイルへのアクセスが完全にブロックされます。

手順については、「 [SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする」を](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)参照してください。

## <a name="can-admins-bypass-disallowinfectedfiledownload-and-extract-infected-files"></a>管理者は *、DisallowInfectedFileDownload* をバイパスし、感染したファイルを抽出できますか?

SharePoint 管理者とグローバル管理者は、 [Get-SPOMalwareFileContent](/powershell/module/sharepoint-online/get-spomalwarefilecontent) コマンドレットを使用して、SharePoint Online PowerShell でマルウェアに感染したファイルのフォレンジック ファイル抽出を実行できます。 管理者は、感染したコンテンツをホストするサイトにアクセスする必要はありません。 ファイルがマルウェアとしてマークされている限り、管理者は **Get-SPOMalwareFileContent** を使用してファイルを抽出できます。 

感染したファイルの詳細については、管理者は **[Get-SPOMalwareFile](/powershell/module/sharepoint-online/get-spomalwarefile)** コマンドレットを使用して、検出されたマルウェアの種類と感染の状態を確認できます。 

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

悪意のあるファイルが OneDrive にアップロードされると、マルウェアとしてマークされる前にローカル コンピューターに同期されます。 マルウェアとしてマークされた後、ユーザーはローカル コンピューターから同期されたファイルを開けなくなります。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365を使用した拡張機能

サブスクリプションに[含まれているか](defender-for-office-365.md)、アドオンとして購入Microsoft Defender for Office 365 Microsoft 365 組織では、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にして、レポートと保護を強化できます。 詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。

## <a name="related-articles"></a>関連記事

[Microsoft 365 のマルウェアとランサムウェアの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online、OneDrive、Microsoft Teams のウイルス対策の詳細については、「 [脅威から保護](protect-against-threats.md) し、 [SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする](turn-on-mdo-for-spo-odb-and-teams.md)」を参照してください。

---
title: SharePoint Online、OneDrive、およびMicrosoft Teamsの組み込みウイルス保護
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
ms.openlocfilehash: ddb424458e991becefb98efbad5b2a86c5f9441c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208903"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、およびMicrosoft Teamsの組み込みウイルス保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

Microsoft 365では、一般的なウイルス検出エンジンを使用して、ユーザーがSharePoint Online、OneDrive、およびMicrosoft Teamsにアップロードするファイルをスキャンします。 この保護は、SharePoint Online、OneDrive、およびMicrosoft Teamsを含むすべてのサブスクリプションに含まれます。

> [!IMPORTANT]
> 組み込みのウイルス対策機能は、ウイルスを含むのに役立つ方法です。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対し、さまざまなレイヤーでマルウェア対策の保護を調査して実装し、エンタープライズ インフラストラクチャをセキュリティで保護するためのベスト プラクティスを適用することをお勧めします。 戦略とベスト プラクティスの詳細については、「 [セキュリティ ロードマップ](security-roadmap.md)」を参照してください。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされた場合はどうなりますか?

Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に (ファイルのアップロードとは独立して) 実行されます。 **すべてのファイルは自動的にスキャンされません**。 ヒューリスティックによって、スキャンするファイルが決定されます。 ファイルにウイルスが含まれていることが検出されると、ファイルにフラグが設定されます。 2018 年 4 月に、スキャンされたファイルの 25 MB の制限を削除しました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。
2. SharePoint Online は、ウイルス スキャン プロセスの一環として、後でファイルがスキャンの条件を満たしているかどうかを判断します。
3. ファイルがスキャンの条件を満たしている場合は、ウイルス検出エンジンによってファイルがスキャンされます。
4. スキャンされたファイル内でウイルスが見つかった場合、ウイルス エンジンは、感染していることを示すプロパティをファイルに設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

ファイルが感染している場合、ユーザーはブラウザーを使用してSharePoint Online からファイルをダウンロードできません。

動作は次のとおりです。

1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
2. ユーザーには、ウイルスが検出されたことを示す警告が表示されます。 既定では、ユーザーにはファイルをダウンロードし、自分のデバイス上のウイルス対策ソフトウェアを使用してファイルのクリーニングを試みるオプションが与えられます。

> [!NOTE]
>
> 管理者は、SharePoint Online PowerShell の [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策の警告ウィンドウでも、感染したファイルをダウンロードできないようにすることができます。 手順については、「[SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする」を](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)参照してください。
>
> *DisallowInfectedFileDownload* パラメーターを有効にするとすぐに、検出されたファイルまたはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

悪意のあるファイルがOneDriveにアップロードされると、マルウェアとしてマークされる前にローカル コンピューターに同期されます。 マルウェアとしてマークされた後、ユーザーはローカル コンピューターから同期されたファイルを開けなくなります。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365を使用した拡張機能

サブスクリプションに[Microsoft Defender for Office 365](defender-for-office-365.md)が含まれている、またはアドオンとして購入した組織Microsoft 365、SharePoint、OneDrive、およびMicrosoft Teamsのセーフ添付ファイルを有効にすることができます レポートと保護を強化します。 詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。

## <a name="related-articles"></a>関連記事

[Microsoft 365のマルウェアとランサムウェアの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online、OneDrive、Microsoft Teamsのウイルス対策の詳細については、「[脅威から保護](protect-against-threats.md)し、[SharePoint、セーフ OneDrive、Microsoft Teamsの添付ファイルを有効にする」を](turn-on-mdo-for-spo-odb-and-teams.md)参照してください。

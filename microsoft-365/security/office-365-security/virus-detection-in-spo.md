---
title: SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス対策
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
description: ユーザーがアップロードするファイルで、SharePoint Online がウイルスを検出し、ユーザーがファイルをダウンロードまたは同期できないようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844238"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 では、ユーザーが SharePoint Online、OneDrive、Microsoft Teams にアップロードするファイルをスキャンするための共通のウイルス検出エンジンを使用しています。 この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。

> [!IMPORTANT]
> 組み込みのウイルス対策機能を使用すると、ウイルスを含めることができます。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査して実装し、企業インフラストラクチャを保護するためのベストプラクティスを適用することをお勧めします。 戦略とベストプラクティスの詳細については、「 [セキュリティロードマップ](security-roadmap.md)」を参照してください。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に実行されます。 **アップロード時にすべてのファイルが自動的にスキャンされることはありません** 。 ヒューリスティックはスキャンするファイルを決定します。 ファイルにウイルスが含まれていることが検出されると、ファイルはフラグが付けられ、再度ダウンロードすることはできません。 2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。
2. SharePoint Online は、ファイルがスキャンの条件を満たしているかどうかを判断します。
3. ウイルス検出エンジンによってファイルがスキャンされます。
4. ウイルスが検出された場合、ウイルスエンジンはそのファイルが感染していることを示すプロパティを設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードすることはできません。

動作は次のとおりです。

1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
2. ウイルスが検出されたという警告がユーザーに提示されます。 既定では、ユーザーはファイルをダウンロードし、自分のデバイスでウイルス対策ソフトウェアを使用してウイルス対策ソフトウェアを使用してクリーニングを試みることができます。

> [!NOTE]
>
> 管理者は、SharePoint Online PowerShell の [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策の警告ウィンドウであっても、感染したファイルをユーザーがダウンロードできないようにすることができます。 手順については、「[SharePoint Online PowerShell を使用して悪意のあるファイルをユーザーがダウンロードできないようにする ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。
>
> *DisallowInfectedFileDownload* パラメーターを有効にすると、ユーザーと管理者に対して、検出/ブロックされたファイルへのアクセスが完全にブロックされます。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

OneDrive 同期クライアントでは、ウイルスが含まれているファイルはダウンロードされません。 ファイルを同期できないという通知が同期クライアントに表示されます。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の拡張機能

Microsoft 365 の組織では、 [Microsoft Defender For Office 365 を](office-365-atp.md) サブスクリプションに含めるか、またはアドオンとして購入することにより、SharePoint、OneDrive、microsoft Teams 用の ATP を有効にして、レポートと保護を強化することができます。 詳細については、「 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)」を参照してください。

## <a name="more-information"></a>詳細情報

SharePoint Online、OneDrive、Microsoft Teams のウイルス対策の詳細については、「 [脅威から保護](protect-against-threats.md) する」と「 [sharepoint、Onedrive、microsoft TEAMS 用の ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。

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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327989"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 では、ユーザーが SharePoint Online、OneDrive、Microsoft Teams にアップロードするファイルをスキャンするための共通のウイルス検出エンジンを使用しています。 この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。

> [!IMPORTANT]
> 組み込みのウイルス対策機能を使用すると、ウイルスを含めることができます。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査して実装し、企業インフラストラクチャを保護するためのベストプラクティスを適用することをお勧めします。 戦略とベストプラクティスの詳細については、「 [セキュリティロードマップ](security-roadmap.md)」を参照してください。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に実行されます。 **アップロード時にすべてのファイルが自動的にスキャンされることはありません**。 ヒューリスティックはスキャンするファイルを決定します。 ファイルにウイルスが含まれていることが検出されると、ファイルはフラグが付けられ、再度ダウンロードすることはできません。 2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。

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
> 管理者は、SharePoint Online PowerShell の[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの*DisallowInfectedFileDownload*パラメーターを使用して、ウイルス対策の警告ウィンドウであっても、感染したファイルをユーザーがダウンロードできないようにすることができます。 手順については、「 [SharePoint Online PowerShell を使用してユーザーが悪意のあるファイルをダウンロードするのを防ぐ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。
>
> *DisallowInfectedFileDownload*パラメーターを有効にすると、ユーザーと管理者に対して、検出/ブロックされたファイルへのアクセスが完全にブロックされます。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

OneDrive 同期クライアントでは、ウイルスが含まれているファイルはダウンロードされません。 ファイルを同期できないという通知が同期クライアントに表示されます。

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a>Office 365 の高度な脅威保護の拡張機能

Microsoft 365 の [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) をサブスクリプションに含めるか、またはアドオンとして購入することにより、SharePoint、OneDrive、microsoft TEAMS で atp を使用して、レポートと保護を強化することができます。 詳細については、「 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)」を参照してください。

## <a name="more-information"></a>詳細情報

SharePoint Online、OneDrive、Microsoft Teams のウイルス対策の詳細については、「 [脅威から保護](protect-against-threats.md) する」と「 [sharepoint、Onedrive、microsoft TEAMS 用の ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。

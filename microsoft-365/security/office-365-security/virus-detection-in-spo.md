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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: SharePoint Online が、ユーザーがアップロードするファイル内のウイルスを検出し、ユーザーがファイルをダウンロードまたは同期する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ba3d19c6b04b93d9b1089540b7483d8b2e7246c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727501"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、Microsoft Teams の組み込みのウイルス保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)

Microsoft 365 は、ユーザーが SharePoint Online、OneDrive、および Microsoft Teams にアップロードするファイルをスキャンするために、一般的なウイルス検出エンジンを使用します。 この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。

> [!IMPORTANT]
> 組み込みのウイルス対策機能は、ウイルスを含むのに役立つ方法です。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査および実装し、企業インフラストラクチャを保護するためのベスト プラクティスを適用してください。 戦略とベスト プラクティスの詳細については、「セキュリティ ロードマップ」 [を参照してください](security-roadmap.md)。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされた場合は、どうなるでしょうか。

Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で (ファイルのアップロードとは独立して) 非同期的に実行されます。 **すべてのファイルは自動的にスキャンされません**。 ヒューリスティックは、スキャンするファイルを決定します。 ファイルにウイルスが含まれていると検出された場合、ファイルにフラグが設定されます。 2018 年 4 月に、スキャンしたファイルの 25 MB の制限が削除されました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。
2. SharePoint Online は、ウイルス スキャン プロセスの一環として、ファイルがスキャンの条件を満たしたかどうかを後で判断します。
3. ファイルがスキャンの条件を満たしている場合、ウイルス検出エンジンはファイルをスキャンします。
4. スキャンしたファイル内でウイルスが検出された場合、ウイルス エンジンはファイルに感染したことを示すプロパティを設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードできます。

動作は次のとおりです。

1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
2. ユーザーには、ウイルスが検出されたという警告が表示されます。 既定では、ユーザーはファイルをダウンロードし、自分のデバイスでウイルス対策ソフトウェアを使用してファイルをクリーンアップするオプションを与えられます。

> [!NOTE]
>
> 管理者は、SharePoint Online PowerShell の [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策の警告ウィンドウでも、ユーザーが感染したファイルをダウンロードすることはできません。 手順については、「Use SharePoint Online PowerShell を使用して、ユーザーが悪意のある [ファイルをダウンロードするのを防ぐ」を参照してください](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。
>
> *DisallowInfectedFileDownload* パラメーターを有効にしたとすぐに、検出またはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

OneDrive 同期クライアントは、ウイルスを含むファイルをダウンロードしません。 ファイルを同期できないという通知が同期クライアントに表示されます。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender 365 用の拡張Office機能

Microsoft Defender for Office [365](office-365-atp.md) がサブスクリプションに含まれているか、アドオンとして購入されている Microsoft 365 組織では、レポートと保護を強化するために SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にできます。 詳細については [、「SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md)の安全な添付ファイル」を参照してください。

## <a name="related-articles"></a>関連記事

[Microsoft 365 のマルウェアとランサムウェアの保護](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online、OneDrive、および Microsoft Teams のウイルス対策の詳細については[](protect-against-threats.md)、「脅威から保護する」および[「SharePoint、OneDrive、](turn-on-atp-for-spo-odb-and-teams.md)および Microsoft Teams の安全な添付ファイルを有効にする」を参照してください。

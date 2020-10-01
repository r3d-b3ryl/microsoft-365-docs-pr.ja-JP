---
title: SharePoint、OneDrive、Microsoft Teams 用の ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online、OneDrive for Business、Microsoft Teams のファイルの Office 365 Advanced Threat Protection について説明します。
ms.openlocfilehash: 194b8e45e573ae4c4cd1f3428a1f80c48e1d80c8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326867"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) は、 [Microsoft 365 の一般的なウイルス検出エンジン](virus-detection-in-spo.md)によってアップロード時に既にスキャンされているファイルに対して、追加の保護レイヤーを提供します。 SharePoint、OneDrive、Microsoft Teams 用の ATP は、チームサイトやドキュメントライブラリに悪意のあるファイルとして識別された既存のファイルを検出してブロックするのに便利です。

既定では、SharePoint、OneDrive、Microsoft Teams 用の ATP は有効になっていません。 これをオンにするには、「 [SharePoint、OneDrive、Microsoft Teams の ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive、Microsoft Teams の ATP のしくみ

SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にし、ファイルを悪意のあるものとして識別すると、ファイルはファイルストアと直接統合してロックされます。 次の図は、ライブラリ内で検出された悪意のあるファイルの例を示しています。

![悪意のあるものとして検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

ブロックされたファイルは、ドキュメントライブラリと web、モバイル、またはデスクトップの各アプリケーションに表示されていますが、ユーザーはファイルを開く、コピー、移動、または共有することはできません。 ただし、ブロックされたファイルを削除することができます。

次に、モバイルデバイスでブロックされるファイルの外観を示します。

![Onedrive モバイルアプリから OneDrive for business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

既定では、ユーザーはブロックされたファイルをダウンロードできます。 ブロックされたファイルをダウンロードする方法を次に示します。モバイルデバイスでは次のように表示されます。

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 管理者は、悪意のあるファイルをユーザーがダウンロードできないようにすることができます。 手順については、「 [SharePoint Online PowerShell を使用してユーザーが悪意のあるファイルをダウンロードするのを防ぐ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。

ファイルが悪意のあるものとして検出された場合のユーザーの操作の詳細については、「 [SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合の対処](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)方法」を参照してください。

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams の ATP によって検出された悪意のあるファイルに関する情報を表示する

ATP で悪意があると識別されたファイルは、 [Office 365 Advanced Threat Protection](view-reports-for-atp.md) および [エクスプローラ (およびリアルタイム検出)](threat-explorer.md)のレポートで表示されます。

2018年5月の時点で、ファイルが ATP によって悪意のあるものと識別されると、ファイルは検疫でも利用できます。 詳細については、「 [セキュリティ & コンプライアンスセンターを使用して検疫済みファイルを管理する](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)」を参照してください。

## <a name="keep-these-points-in-mind"></a>これらの点を念頭に置いてください。

- ATP では、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルがスキャンされるわけではありません。 この動作は仕様です。 ファイルは非同期でスキャンされます。 このプロセスでは、スマートヒューリスティックおよび脅威信号と共に、共有とゲストのアクティビティイベントを使用して、悪意のあるファイルを特定します。

- SharePoint サイトが [モダンな環境](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)を使用するように構成されていることを確認します。 ATP 保護は、モダンな表示とクラシック表示のどちらを使用するかに適用されます。ただし、ファイルがブロックされているという視覚インジケーターは、モダンな環境でのみ利用可能です。

- SharePoint、OneDrive、Microsoft Teams 用の ATP は、組織の全体的な脅威保護戦略に含まれています。これには、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、および Office 365 ATP の安全なリンクと安全な添付ファイルが含まれます。 詳細については、「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。

---
title: SPO、OneDrive、Teams 用の安全な添付ファイル機能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online、OneDrive for Business、Microsoft TeamsのファイルのMicrosoft Defender for Office 365について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 220bb976ebe701e5db5f03370a1a7c188f197cb1
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475765"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SPO、OneDrive、Teams 用の安全な添付ファイル機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365のSharePoint、OneDrive、およびMicrosoft Teamsの[添付ファイルセーフ](whats-new-in-defender-for-office-365.md)、[共通のウイルス検出エンジンによって既に非同期的にスキャンされたファイルに対する追加の保護レイヤーが提供されます。Microsoft 365](virus-detection-in-spo.md)。 SharePoint、OneDrive、Microsoft Teamsの添付ファイルをセーフすると、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別される既存のファイルを検出してブロックできます。

既定では、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは有効になっていません。 これを有効にするには、「SharePoint、[OneDrive、Microsoft Teamsの添付ファイルセーフ有効にする](turn-on-mdo-for-spo-odb-and-teams.md)」を参照してください。

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive、Microsoft Teamsの添付ファイルをセーフする方法

SharePoint、OneDrive、およびMicrosoft Teamsの添付ファイルをセーフしてファイルを悪意のあるものとして識別すると、ファイル ストアとの直接統合を使用してファイルがロックされます。 次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。

:::image type="content" source="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png" alt-text="悪意のあるファイルとして検出されたOneDrive for Business内のファイル" lightbox="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png":::

ブロックされたファイルは、ドキュメント ライブラリおよび Web、モバイル、もしくはデスクトップ アプリケーションにまだ表示されていますが、ファイルを開く、コピー、移動、または共有することはできません。 ただし、ブロックされたファイルは削除できます。

次に、モバイル デバイスでブロックされたファイルがどのように表示されるかという例を示します。

:::image type="content" source="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png" alt-text="OneDrive モバイル アプリからブロックされたファイルをOneDrive for Businessから削除するオプション" lightbox="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png":::

規定では、ユーザーはブロックされたファイルをダウンロードすることが可能です。 ブロックされたファイルをモバイル デバイスでダウンロードする方法を次に示します。

:::image type="content" source="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png" alt-text="OneDrive for Businessでブロックされたファイルをダウンロードするオプション" lightbox="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png":::

SharePoint Online 管理者は、悪意のあるファイルをユーザーがダウンロードできないようにすることができます。 手順については、「[SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする」を](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)参照してください。

ファイルが悪意のあるファイルとして検出された場合のユーザー エクスペリエンスの詳細については、「[SharePoint Online、OneDrive、またはMicrosoft Teamsで悪意のあるファイルが見つかった場合の対処方法](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)」を参照してください。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルによって検出された悪意のあるファイルに関する情報を表示する

SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルによって悪意のあるファイルとして識別されたファイルは、Microsoft Defender for Office 365および[エクスプローラー (およびリアルタイム検出)](threat-explorer.md) の[レポート](view-reports-for-mdo.md)に表示されます。

SharePoint、OneDrive、Microsoft Teamsの添付ファイルをセーフして悪意のあるファイルとして識別された場合、ファイルは検疫でも使用できますが、管理者のみが使用できます。 詳細については、「[Defender for Office 365で検疫されたファイルを管理する](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)」を参照してください。

## <a name="keep-these-points-in-mind"></a>これらの点に留意してください

- Defender for Office 365は、SharePoint Online、OneDrive for Business、またはMicrosoft Teams内のすべてのファイルをスキャンしません。 この動作は仕様です。 ファイルは非同期的にスキャンされます。 このプロセスでは、共有イベントとゲスト アクティビティ イベント、スマート ヒューリスティックおよび脅威シグナルを使用して、悪意のあるファイルを識別します。

- SharePoint サイトが [Modern エクスペリエンス](/sharepoint/guide-to-sharepoint-modern-experience)を使用するように構成されていることを確認します。 Defender for Office 365保護は、モダン エクスペリエンスとクラシック ビューのどちらを使用するかに関係なく適用されます。ただし、ファイルがブロックされていることを示す視覚的なインジケーターは、モダン エクスペリエンスでのみ使用できます。

- SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルは、組織の全体的な脅威保護戦略の一部です。これには、Exchange Online Protection (EOP) でのスパム対策とマルウェア対策の保護、セーフリンクとMicrosoft Defender for Office 365で添付ファイルをセーフします。 詳細については、「[Office 365の脅威から保護する](protect-against-threats.md)」を参照してください。

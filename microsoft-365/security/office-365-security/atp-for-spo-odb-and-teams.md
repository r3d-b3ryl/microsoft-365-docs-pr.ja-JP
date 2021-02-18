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
localization_priority: Normal
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
description: Microsoft Defender for Office 365 for files in SharePoint Online, OneDrive for Business, and Microsoft Teams について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce73e1fd5c8ecb63bee1db2e9e64aade305b37e9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287055"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SPO、OneDrive、Teams 用の安全な添付ファイル機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Microsoft Defender for Office 365](office-365-atp.md)の SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは[、Microsoft 365](virus-detection-in-spo.md)の一般的なウイルス検出エンジンによってアップロード時に既にスキャンされたファイルに対する保護層を追加します。 SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別された既存のファイルを検出してブロックするのに役立ちます。

SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは、既定では有効になっていません。 有効にする方法については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルのしくみ

SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが有効で、ファイルが悪意のあるファイルとして識別される場合、ファイル ストアとの直接統合を使用してファイルがロックされます。 次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。

![悪意のあるファイルとして検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

ブロックされたファイルは引き続きドキュメント ライブラリと Web アプリケーション、モバイル アプリケーション、またはデスクトップ アプリケーションに表示されます。ただし、ユーザーはファイルを開く、コピーする、移動する、または共有できません。 ただし、ブロックするファイルは削除できます。

モバイル デバイスでブロックされるファイルの例を次に示します。

![OneDrive モバイル アプリから OneDrive for Business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

既定では、ユーザーはブロックされたファイルをダウンロードできます。 ブロックするファイルをモバイル デバイスでダウンロードする方法を次に示します。

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 管理者は、悪意のあるファイルをダウンロードするユーザーを防止できます。 手順については [、「SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードするのを防ぐ」を参照してください](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。

ファイルが悪意のあるファイルとして検出された場合のユーザー エクスペリエンスの詳細については [、「SharePoint Online、OneDrive、または Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)で悪意のあるファイルが見つかった場合の対応方法」を参照してください。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルによって検出された悪意のあるファイルに関する情報を表示する

Office 365 の Microsoft Defender によって悪意のあるファイルとして識別されたファイルは [、microsoft Defender for Office 365](view-reports-for-atp.md) およびエクスプローラー (およびリアルタイムの検出 [)](threat-explorer.md)のレポートに表示されます。

2018 年 5 月の現在、ファイルが Office 365 の Microsoft Defender によって悪意のあるファイルとして識別された場合、そのファイルは検疫でも使用できます。 詳細については、「セキュリティ/コンプライアンス センター [を使用して&ファイルを管理する」を参照してください](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)。

## <a name="keep-these-points-in-mind"></a>以下の点を念頭に置く

- Defender for Office 365 は、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルをスキャンする必要があります。 この動作は仕様です。 ファイルは非同期的にスキャンされます。 このプロセスでは、共有イベントとゲスト アクティビティ イベントをスマート ヒューリスティックや脅威シグナルと共に使用して、悪意のあるファイルを特定します。

- SharePoint サイトがモダン エクスペリエンスを使用するように構成されていることを [確認します](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。 Defender for Office 365 保護は、モダン エクスペリエンスとクラシック ビューの使用に関して適用されます。ただし、ファイルがブロックされている視覚的なインジケーターは、モダン エクスペリエンスでのみ使用できます。

- SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルは、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、Microsoft Defender for Office 365 の安全なリンクと安全な添付ファイルを含む、組織の全体的な脅威保護戦略の一部です。 詳細については、「Office [365」を参照](protect-against-threats.md)してください。

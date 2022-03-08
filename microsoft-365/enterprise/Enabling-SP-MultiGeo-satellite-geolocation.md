---
title: サテライト地域で SharePoint Multi-Geo の有効化
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: この記事では、グローバル管理者または管理者SharePoint、サテライト地域の場所で複数地域SharePointを有効にするための情報を提供します。
ms.openlocfilehash: b542c1ee77c7b4ca7a6179bac5ce5eaa1090606a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330441"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>サテライト地域で SharePoint Multi-Geo の有効化

この記事は、2019 年 3 月 27日に SharePoint Multi-Geo の機能が一般的に利用できるようになる **前に**、Multi-Geo のサテライト地域を作成した Global または SharePoint の管理者、およびサテライト地域で SharePoint Multi-Geo を有効にしていないユーザー向けのものです。 

>[!Note]
>**2019** 年 3 月 27 日以降に新しい地域の場所を追加した場合は、新しい地域の場所が OneDrive および SharePoint Multi-Geo に対して既に有効になっているので、これらの手順を実行する必要があります。

以下の手順により、ユーザーのサテライト地域で SharePoint を有効にできるため、Multi-Geo サテライト ユーザーは O365 で、OneDrive と SharePoint Multi-Geo 両方の機能を利用できるようになります。 

>[!IMPORTANT]
>これは有効化の方法の 1 つであることに注意してください。 SPO モードを設定したら、サポートによるエスカレーションなしでテナントを OneDrive の Multi-Geo モードに戻すことだけはできません。 

## <a name="to-set-a-geo-location-into-spo-mode"></a>SPO モードに地域を設定するには

SPO モードに地域を設定するには、SPO モードで設定する地域に接続します。

1.    SharePoint Online 管理シェルを開く 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience。](../media/Set-SPO-MultiGeo.jpg)
4.    この操作は通常 1 時間程度かかり、その間、サービス内でさまざまな発行バックを実行し、テナントに再度スタンプを付けます。 少なくとも 1 時間後に Get-SPOMultiGeoExperience を実行してください。  実行すると、SPO モードにこの地域があるかどうかが表示されます。</br></br>
![Set-SPOMultiGeoExperience。](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>サービスの特定のキャッシュは 24 時間ごとに更新するため、最大で 24 時間、ODB モードのままであるかのように、サテライト地域が断続的に動作する可能性があります。 この動作により技術的な問題が発生することはありません。 
 
SharePoint Multi-Geo に関する詳細については [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md) を参照してください。



---
title: OneDrive および SharePoint Online の複数地域機能
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: OneDrive Online の複数地域機能を使用して、複数の地域に Microsoft 365 のプレゼンスを展開します。
ms.openlocfilehash: e49df6054e30e9e288e893da8d914ebb567eb8e5
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622220"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>OneDrive および SharePoint Online の複数地域機能

OneDriveおよびSharePoint Online の複数地域機能を使用すると、SharePoint チーム サイトやMicrosoft 365グループ メールボックスなどの共有リソースを、指定された地理的な場所に保存して保存できます。

各ユーザー、グループ メールボックス、およびSharePoint サイトには、関連データを格納する地理的な場所を示す優先データの場所 (PDL) があります。 ユーザーの個人データ (Exchange メールボックスと OneDrive) を、本人が作成した Microsoft 365 グループまたは SharePoint サイトと共に指定された地域の場所に格納して、データ所在地の要件を満たすことができます。 [地域の場所ごとに異なる管理者を指定する](add-a-sharepoint-geo-admin.md)ことができます。

ユーザーが Office アプリケーション、OneDrive、Search などの Microsoft 365 サービスを使用するとき、シームレスなエクスペリエンスが可能になります。 詳細については、「[複数地域環境でのユーザー エクスペリエンス](multi-geo-user-experience.md)」を参照してください。

## <a name="onedrive"></a>OneDrive

各ユーザーの OneDrive は、ユーザーの PDL に従ってサテライトの場所でプロビジョニングされるか、または[管理者が移動させる](move-onedrive-between-geo-locations.md)ことができます。 個人用ファイルはその地域の場所に保存されますが、他の地域の場所にいるユーザーと共有することも可能です。

## <a name="sharepoint-sites-and-groups"></a>SharePoint サイトとグループ

複数地域機能の管理は、<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理センター</a>から入手できます。 詳細な情報は[対応するブログ記事](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)にあります。

ユーザーが複数地域環境でSharePointグループ接続サイトを作成すると、PDL を使用して、サイトとその関連するグループ メールボックスが作成される地域の場所が決定されます。 (ユーザーの PDL 値が設定されていない場合、またはサテライトの場所として構成されていない地域の場所に設定されている場合、サイトとメールボックスは中央の場所に作成されます)。

Exchange、OneDrive、SharePoint、Teams以外のMicrosoft 365 サービスは複数地域ではありません。 ただし、これらのサービスによって作成されるMicrosoft 365 グループは、作成者の PDL とそのExchange グループ メールボックスで構成されます。SharePoint サイトは対応する geo でプロビジョニングされます。 

## <a name="managing-the-multi-geo-environment"></a>複数地域環境の管理

複数地域環境の設定と管理は<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">、SharePoint管理センター</a>を通じて行われます。 

![SharePoint管理センターの [地域の場所] ページのスクリーンショット。](../media/sharepoint-multi-geo-admin-center.png)

(SharePoint サイトや OneDrive サイトを移動するなど、一部の操作では Microsoft PowerShell が必要です。)

## <a name="see-also"></a>関連項目

[SharePoint および Microsoft 365 グループでの複数地域機能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[複数地域環境の管理](administering-a-multi-geo-environment.md)

[複数地域環境における SharePoint ストレージ クォータ](sharepoint-multi-geo-storage-quota.md)

[複数地域環境での Exchange Online メールボックスの管理](administering-exchange-online-multi-geo.md)

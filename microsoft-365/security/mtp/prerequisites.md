---
title: Microsoft Threat Protection の前提条件
description: Microsoft Threat Protection のライセンス、ハードウェアとソフトウェアの要件、およびその他の構成設定について学習する
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、MTP、M365、license、E5、A5、EMS、購入
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 66b3f7e446416b6252050e6f41a2b22d99d25767
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209237"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Microsoft Threat Protection の前提条件

**適用対象:**
- Microsoft Threat Protection

Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。

## <a name="licensing-requirements"></a>ライセンス要件

>[!IMPORTANT]
>2020年5月12日から、Microsoft は、ライセンス要件に関して最適化された新しいエクスペリエンスを徐々にロールアウトし、 [microsoft の脅威保護を有効に](mtp-enable.md)します。 この期間中、一部のお客様は、ポータルエクスペリエンスへの変更を確認し始めます。 この記事では、新しいエクスペリエンスに関する情報を**新しいエクスペリエンス**としてマークしています。

Microsoft の脅威保護を使用するには、1つのライセンスまたはライセンスの組み合わせが必要です。 これらのライセンスまたはライセンスの組み合わせによって、追加のコストを必要とせずに Microsoft の脅威保護機能にアクセスできるようになります。

### <a name="single-license"></a>単一のライセンス
次の*いずれか*のライセンスを使用できます。

- Microsoft 365 E5 または A5
- Microsoft 365 E5 セキュリティまたは A5 セキュリティ

### <a name="combination-of-licenses"></a>ライセンスの組み合わせ
また、Office 365、 *Enterprise Mobility + Security (EMS)*、および Windows に対して、E5 または A5 サブスクリプションのライセンスを組み合わせて使用することもできます。 ライセンスの組み合わせには、これらのライセンスの*すべて*が含まれている必要があります。

- Office 365 E5 または A5
- *Enterprise Mobility + Security (EMS)* E5 または A5
- Windows 10 Enterprise E5 または A5

詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。

> まだライセンスを持っていませんか? [Microsoft 365 サブスクリプションを試用または購入する](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


**新しい作業:** 2020年5月12日から、ユーザーはこの操作に対する変更を段階的に受け取ります。 新機能を使用する場合は、次のいずれかのライセンスを持つ*すべて*のお客様が Microsoft の脅威保護を有効にするオプションを利用できます。

- Microsoft 365 E5 または A5
- Microsoft 365 E5 セキュリティまたは A5 セキュリティ
- Windows 10 Enterprise E5 または A5
- Enterprise Mobility + Security (EMS) E5 または A5 
- Office 365 E5 または A5
- Microsoft Defender Advanced Threat Protection 
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security 
- Office 365 Advanced Threat Protection (プラン 2) 

### <a name="check-your-existing--licenses"></a>既存のライセンスを確認する
Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。 管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。

>[!NOTE]
> ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者**または**グローバル閲覧**者の役割のいずれかが割り当てられている必要があります。 アクセスの問題が発生した場合は、グローバル管理者に連絡してください。

## <a name="browser-requirements"></a>ブラウザー要件
Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスします。

## <a name="us-gcc-and-gcc-high-availability"></a>US GCC および GCC 高可用性
現時点では、Microsoft の脅威保護は米国政府機関向けの Community Cloud (GCC) および Government Community Cloud High (GCC High) のお客様にはご利用いただけません。 

## <a name="related-topics"></a>関連項目
- [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
- [Microsoft Threat Protection を有効にする](mtp-enable.md)

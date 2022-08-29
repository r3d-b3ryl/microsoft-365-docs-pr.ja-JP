---
title: Microsoft Defender for Businessでポリシーの順序を理解する
description: Defender for Business を使用して会社のデバイスを保護するためのサイバーセキュリティ ポリシーの優先順位について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 4d3f2f7a04891fdf3e08f06d6744894e18e944dd
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320352"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでポリシーの順序を理解する

## <a name="policy-order-in-defender-for-business"></a>Defender for Business のポリシー順序

Defender for Business には、従業員が使用するデバイスが確実に保護されるように、定義済みのポリシーが含まれています。 セキュリティ チームは、新しいポリシーを追加することもできます。 たとえば、一部のデバイスに特定の設定を適用し、他のデバイスに異なる設定を適用するとします。 これを行うには、次世代の保護ポリシーやファイアウォール ポリシーなどのポリシーを追加します。

ポリシーが追加されると、優先度の順序が割り当てられていることがわかります。 定義するポリシーの優先度の順序は編集できますが、既定のポリシーの優先度の順序は変更できません。 たとえば、Windows クライアント デバイスには、3 つの次世代保護ポリシーがあるとします。 この場合、既定のポリシーの優先度は 3 です。 1 と 2 の番号が付いたポリシーの順序を変更できますが、既定のポリシーはリスト内の 3 番目の番号のままになります。 

**複数のポリシーについて覚えておく必要がある重要な点は、デバイスが最初に適用されたポリシーのみを受け取るということです。** 3 つの次世代ポリシーの前の例を参照すると、3 つのポリシーすべてで対象となるデバイスがあるとします。 この場合、これらのデバイスはポリシー番号 1 を受け取りますが、2 と 3 という番号のポリシーは受け取りません。 

## <a name="key-points-to-remember-about-policy-order"></a>ポリシーの順序について覚えておく必要がある重要なポイント

- ポリシーには優先順位が割り当てられます。
- デバイスは、最初に適用されたポリシーのみを受け取ります。
- ポリシーの優先度の順序を変更できます。
- 既定のポリシーには、優先度の最も低い順序が与えられます。

## <a name="next-steps"></a>次の手順

- [Defender for Business の使用を開始する](mdb-get-started.md)
- [デバイスの管理](mdb-manage-devices.md)
- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
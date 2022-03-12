---
title: Microsoft Defender for Business のポリシーの順序を理解する
description: Microsoft Defender for Business のポリシーを使用した優先度の順序について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 1b2b171c6872cd7ff555a92bcd88b50fa0ff4880
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449177"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>Microsoft Defender for Business のポリシーの順序を理解する

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。[](../../business-premium/index.md) スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

## <a name="policy-order-in-microsoft-defender-for-business"></a>Microsoft Defender for Business のポリシーの順序

Microsoft Defender for Business には、従業員が使用するデバイスを保護するための定義済みのポリシーが含まれています。 セキュリティ チームは、新しいポリシーも追加できます。 たとえば、特定の設定を一部のデバイスに適用し、他のデバイスに異なる設定を適用するとします。 これを行うには、次世代の保護ポリシーやファイアウォール ポリシーなどのポリシーを追加します。

ポリシーが追加されるに従って、優先度の順序が割り当てられているのが分かっています。 定義したポリシーの優先度の順序は編集できますが、既定のポリシーの優先度の順序は変更できます。 たとえば、クライアント デバイスWindows、次の世代の保護ポリシーが 3 つあるとします。 この場合、既定のポリシーの優先度は 3 です。 1 と 2 の番号が付いたポリシーの順序を変更できますが、既定のポリシーはリストの番号 3 のままです。 

**複数のポリシーについて覚えておく必要がある重要な点は、デバイスが最初に適用されたポリシーのみを受け取る点です。** 3 つの次世代ポリシーの前の例を参照して、3 つのポリシーすべてによって対象となるデバイスがある場合を考えます。 この場合、これらのデバイスはポリシー番号 1 を受信しますが、2 と 3 という番号のポリシーは受信されません。 

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="key-points-to-remember-about-policy-order"></a>ポリシーの順序に関する注意点

- ポリシーには優先度の順序が割り当てられます。

- デバイスは、最初に適用されたポリシーのみを受け取る。

- ポリシーの優先度を変更できます。

- 既定のポリシーには、優先度の最も低い順序が与えられる。

## <a name="next-steps"></a>次の手順

- [Defender for Business の使用を開始する](mdb-get-started.md)

- [デバイスの管理](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
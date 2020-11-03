---
title: Microsoft 365 Defender
description: Microsoft 365 Defender は、デバイス、id、データ、およびアプリケーションを保護するように設計された、調整された脅威保護ソリューションです。
keywords: Microsoft の脅威保護、サイバーセキュリティ、高度な常設脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索などについて説明します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: a8d25ba0b36ad6ba1651ffe19e3e2f6e241548c7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843806"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



Microsoft 365 Defender は、統合された事前違反のエンタープライズ防御スイートであり、エンドポイント、id、電子メール、およびアプリケーション間の応答をネイティブに調整し、高度な攻撃から統合された保護を提供します。

統合された Microsoft 365 Defender ソリューションを使用することにより、セキュリティ担当者は、これらの各製品が脅威のすべての範囲と影響を受信して判断することを伝える脅威について協力することができます。環境にどのように対応したか、どのような影響を受けるか、どのように組織にどのように影響しているか。 Microsoft 365 Defender は、攻撃を阻止または停止する、または影響を受けるメールボックス、エンドポイント、ユーザー id を自己回復させるための自動操作を行います。  


<center><h2>Microsoft 365 Defender サービス</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>エンドポイントの Microsoft Defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Id の Microsoft Defender</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>この [Microsoft 365 Defender interactive ガイド](https://aka.ms/MTP-Interactive-Guide)をご確認ください。


Microsoft 365 Defender suite は次のものを保護します。 
- エンドポイント **の Microsoft defender を使用した** エンドポイント-エンドポイントの microsoft defender は、予防的な保護、ブリーチ後の検出、自動化された調査、応答のための統合エンドポイントプラットフォームです。 
- **電子メールとコラボレーション Microsoft defender For office 365** -Defender for office 365 は、電子メールメッセージ、リンク (url) およびコラボレーションツールによってもたらされる悪意のある脅威から組織を保護します。 
- Id **および AZURE AD Identity Protection に関する Microsoft defender** の Id。 id の microsoft defender では、Active Directory のシグナルを使用して、組織での高度な脅威、侵害された id、および悪意のある insider 操作を識別、検出、調査します。 
- **Microsoft Cloud app security を使用したアプリケーション** -Microsoft cloud app security は、高度な可視性、強力なデータ制御、および拡張された脅威保護をクラウドアプリにもたらす包括的な相互 SaaS ソリューションです。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender の独自のクロス積層は、個々のスイートコンポーネントを次のように強化します。
- 脅威からの保護、および自動アクションによるスイート全体にわたる防御応答の調整に役立つ
- 警告、疑わしいイベント、影響を受ける資産のデータを「インシデント」に結合することによって、セキュリティチームのすべての製品のアラート、動作、およびコンテキストにわたる攻撃の全記事を語る
- 自動修復によって影響を受ける資産の自己復旧を開始することにより、侵害への対応を自動化する
- エンドポイントと Office データにわたって、セキュリティチームが詳細で効果的な脅威を探すことができるようにする

![インシデントの概要ページの画像](../../media/overview-incident.png) <br>
製品間のインシデント (概要)

![通知キューの画像](../../media/incident-list.png)<br>
Suite 製品全体で関連付けられているすべての通知を1つのインシデント ([alerts] ビュー) に関連付けます。

![インシデントキューの画像](../../media/advanced-hunting.png)<br>
電子メールとエンドポイントの生データを検索するクエリベースの検索


Microsoft 365 Defender クロス製品機能には、次のようなものがあります。 
- **製品間での単一ウィンドウの** 中央表示ウィンドウ検出、影響を受ける資産、実行された操作、および関連する証拠に関するすべての情報が、 [security.microsoft.com](https://security.microsoft.com)の単一のキューおよび単一のウィンドウに表示されます。 
- **組み合わされたインシデントキュー** -セキュリティ担当者が、完全な攻撃範囲を確保し、影響を受けるリソースと自動修復アクションをグループ化し、タイムリーに提示します。 
- **脅威に** 重大な脅威に対する自動応答は、Microsoft 365 Defender 製品間のリアルタイムで共有され、攻撃の進行を止めることができます。 たとえば、エンドポイントの Microsoft Defender で保護されているエンドポイントで悪意のあるファイルが検出された場合、Office 365 に対して、すべての電子メールメッセージのファイルをスキャンして削除するように指示します。 このファイルは、Microsoft 365 セキュリティスイート全体によって表示がブロックされます。
- 侵害された **デバイス、ユーザー id、メールボックスに対する自己復旧** -Microsoft 365 Defender は、影響を受けた自動アクションおよびプレイブックを使用して、影響を受けるアセットをセキュリティで保護された状態に戻します。 Microsoft 365 Defender は、スイート製品の自動修復機能を活用して、インシデントに関連する影響を受けるすべての資産を可能な限り自動的に修復します。
- **クロス積脅威** 検索-セキュリティチームは、さまざまな保護製品によって収集された生データに対して独自のカスタムクエリを作成することによって、組織の独自の知識を活用して、侵害の兆候を探すことができます。 Microsoft 365 Defender では、エンドポイント間の過去30日間の生の信号とアラートデータ、および Office 365 データの Microsoft Defender に対するクエリベースのアクセスが提供されています。 


## <a name="get-started"></a>作業の開始
Microsoft 365 セキュリティセンターの [security.microsoft.com](https://security.microsoft.com)でサービスを有効にするには、Microsoft 365 Defender ライセンスの要件を満たす必要があります。 詳細については、以下を参照してください。
- [ライセンス要件](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender をオンにする](mtp-enable.md)

---
title: Microsoft Threat Protection
description: Microsoft の脅威保護は、デバイス、id、データ、およびアプリケーションを保護するために設計された、調整された脅威保護ソリューションです。
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: b11daf1cc6921e4be87b1bd3965adc2d76d0a0dd
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049930"
---
# <a name="microsoft-threat-protection"></a>Microsoft Threat Protection

**適用対象:**
- Microsoft Threat Protection



Microsoft Threat Protection は、統合された事前違反および事後侵害のエンタープライズ防衛スイートであり、エンドポイント、id、電子メール、およびアプリケーション間の応答をネイティブに調整し、高度な攻撃から統合された保護を提供します。

統合された Microsoft の脅威保護ソリューションを使用することで、セキュリティ担当者は、これらの各製品が脅威のすべての範囲と影響を受信して判断することを伝える脅威に対して協力することができます。環境にどのように対応したか、どのような影響を受けるか、どのように組織にどのように影響しているか。 Microsoft の脅威保護は、攻撃を阻止または停止したり、影響を受けるメールボックス、エンドポイント、ユーザー id を自己回復させるための自動操作を行います。  


<center><h2>Microsoft Threat Protection サービス</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender Advanced Threat Protection</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Office 365 Advanced Threat Protection</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure Advanced Threat Protection</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>この[Microsoft Threat Protection の対話的なガイド](https://aka.ms/MTP-Interactive-Guide)をご覧ください。


Microsoft Threat Protection スイートは以下を保護します。 
- **Microsoft DEFENDER atp があるエンドポイント**-MICROSOFT defender atp は、予防的な保護、ブリーチ後の検出、自動化された調査、および応答のための統合エンドポイントプラットフォームです。 
- **Office 365 を使用した電子メールとコラボレーション**-OFFICE 365 atp は、電子メールメッセージ、リンク (url)、およびコラボレーションツールがもたらす悪意のある脅威から組織を保護します。 
- Azure **atp と AZURE AD Identity Protection を使用した id** azure atp では、Active Directory シグナルを使用して、組織での高度な脅威、侵害された id、および悪意のある insider 操作を識別、検出、調査します。 
- **Microsoft Cloud app security を使用したアプリケーション**-Microsoft cloud app security は、高度な可視性、強力なデータ制御、および拡張された脅威保護をクラウドアプリにもたらす包括的な相互 SaaS ソリューションです。 

Microsoft の脅威保護の独自のクロス積層は、個々のスイートコンポーネントを次のように強化します。
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


Microsoft の脅威保護の製品間の機能には、次のようなものがあります。 
- **製品間での単一ウィンドウの**中央表示ウィンドウ検出、影響を受ける資産、実行された操作、および関連する証拠に関するすべての情報が、 [security.microsoft.com](https://security.microsoft.com)の単一のキューおよび単一のウィンドウに表示されます。 
- **組み合わされたインシデントキュー** -セキュリティ担当者が、完全な攻撃範囲を確保し、影響を受けるリソースと自動修復アクションをグループ化し、タイムリーに提示します。 
- **脅威に**とって重要な脅威に対する自動応答は、Microsoft の脅威保護製品間でリアルタイムで共有されるため、攻撃の進行を停止できます。 たとえば、Microsoft Defender ATP で保護されているエンドポイントで悪意のあるファイルが検出された場合は、Office 365 ATP に対して、すべての電子メールメッセージからファイルをスキャンして削除するように指示します。 このファイルは、Microsoft 365 セキュリティスイート全体によって表示がブロックされます。
- 侵害された**デバイス、ユーザー id、メールボックスに対する自己復旧**-Microsoft の脅威保護は、影響を受けた自動アクションおよびプレイブックを使用して、影響を受けるアセットをセキュリティで保護された状態に戻します。 Microsoft の脅威保護は、スイート製品の自動修復機能を活用して、インシデントに関連する影響を受けるすべての資産が可能な場合に自動的に修復されるようにします。
- **クロス積脅威**検索-セキュリティチームは、さまざまな保護製品によって収集された生データに対して独自のカスタムクエリを作成することによって、組織の独自の知識を活用して、侵害の兆候を探すことができます。 Microsoft の脅威保護では、エンドポイントと Office 365 の ATP データに対して、30日間の履歴生信号およびアラートデータに対するクエリベースのアクセスが提供されています。 


## <a name="get-started"></a>概要
Microsoft 365 セキュリティセンターの[security.microsoft.com](https://security.microsoft.com)でサービスを有効にするには、Microsoft の脅威保護ライセンスの要件を満たす必要があります。 詳細については、以下を参照してください。
- [ライセンス要件](prerequisites.md#licensing-requirements)
- [Microsoft Threat Protection を有効にする](mtp-enable.md)

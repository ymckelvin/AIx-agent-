# Design System Contract

用于冻结项目级设计系统。所有后续 agent 必须遵守此合同。

```yaml
design_system_contract:
  project_name: ""
  status:
    mode: uploaded | default | inferred | locked
    confidence: high | medium | low
    requires_user_confirmation: true | false

  brand_assets:
    logo:
      source: uploaded_asset | placeholder | none
      file: ""
      usage_rule:
        - must_use_original_file
        - no_recolor
        - no_redraw
        - no_distort
        - no_shadow_unless_specified
      placement_default:
        pc_banner: left_or_optional
        mobile_popup: top_center
        pc_popup: top_left

    hero_symbol:
      source: uploaded_asset | generated | placeholder | none
      file: ""
      usage_rule:
        - must_use_original_file
        - preserve_shape
        - preserve_gradient
        - preserve_negative_space
        - no_redraw
        - no_unapproved_style_transfer

  colors:
    primary: "#82F47C"
    secondary: "#C7F06C"
    accent: "#34CEE8"
    background: ["#F4FFF6", "#F7FFF2", "#EFFFF8"]
    text_primary: "#12352B"
    text_secondary: "#2F4A40"
    cta_dark: "#00291F"

  typography:
    zh_font: "PingFang SC"
    fallback: ["Noto Sans CJK SC", "Microsoft YaHei", "sans-serif"]
    title_weight: 700
    body_weight: 400
    cta_weight: 700
    forbidden:
      - serif
      - handwritten
      - calligraphy
      - ai_generated_text
      - distorted_text

  components:
    card_radius: 72
    button_radius: 58
    tag_radius: 28
    shadow_style: restrained

  design_tone:
    - clean
    - restrained
    - product_launch
    - platform_level

  forbidden:
    - no_logo_redraw
    - no_visual_asset_redraw
    - no_text_as_image_for_final_delivery
    - no_red_orange_promotion_style
    - no_dark_tech_style
    - no_complex_3d
```

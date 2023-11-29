load("@stb//:stb.bzl", "stb_library")

STB_COPTS = [
    # "-Wno-sign-conversion",
    # "-Wno-conversion",
    # "-Wno-old-style-cast",
    # "-Wno-useless-cast",
    # "-Wno-shadow",
    # "-Wno-double-promotion",
    # "-Wno-unused-parameter",
    # "-Wno-maybe-uninitialized",
    # "-Wno-type-limits",
    # "-Wno-zero-as-null-pointer-constant",
    # "-Wno-cast-qual",
]

stb_library(
    name = "c_lexer",
    emit_definition_macro = "STB_C_LEXER_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "connected_components",
    emit_definition_macro = "STB_CONNECTED_COMPONENTS_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "divide",
    emit_definition_macro = "STB_DIVIDE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "ds",
    emit_definition_macro = "STB_DS_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "dxt",
    emit_definition_macro = "STB_DXT_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "easy_font",
    emit_definition_macro = "STB_EASY_FONT_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "herringbone_wang_tile",
    emit_definition_macro = "STB_HERRINGBONE_WANG_TILE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "hexwave",
    emit_definition_macro = "STB_HEXWAVE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "image",
    emit_definition_macro = "STB_IMAGE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "image_resize2",
    emit_definition_macro = "STB_IMAGE_RESIZE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "image_write",
    emit_definition_macro = "STB_IMAGE_WRITE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "include",
    emit_definition_macro = "STB_INCLUDE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "leakcheck",
    emit_definition_macro = "STB_LEAKCHECK_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "perlin",
    emit_definition_macro = "STB_PERLIN_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "rect_pack",
    emit_definition_macro = "STB_RECT_PACK_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "sprintf",
    emit_definition_macro = "STB_SPRINTF_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "textedit",
    emit_definition_macro = "STB_TRUETYPE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "tilemap_editor",
    emit_definition_macro = "STB_TRUETYPE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "truetype",
    emit_definition_macro = "STB_TRUETYPE_IMPLEMENTATION",
    copts = STB_COPTS
)

stb_library(
    name = "stretchy_buffer",
    stb_prefix = False
)

# stb_vorbis has a reversed mechanism
genrule(
    name = "vorbis_definition",
    outs = ["stb_vorbis.cpp"],
    cmd  = 'echo "#include <stb/{0}>" > $(@D)/{1}'.format(
        "stb_vorbis.c", "stb_vorbis.cpp"
    ),
    visibility = ["//visibility:private"],
)
cc_library(
    name = "vorbis-private",
    hdrs = ["src/stb_vorbis.c"],
    strip_include_prefix = "src",
    include_prefix = "stb",
    srcs = ["stb_vorbis.cpp"],
    copts = STB_COPTS + ["-Wno-unused-value"],
    visibility = ["//visibility:private"],
)
cc_library(
    name = "vorbis",
    deps = ["//:vorbis-private"],
    defines = ["STB_VORBIS_HEADER_ONLY"],
    visibility = ["//visibility:public"],
)
